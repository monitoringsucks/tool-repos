About
=====
Adagios is a web based Nagios configuration interface built to be simple and intuitive in design, exposing less of the clutter under the hood of nagios. Additionally adagios has a rest interface for both status and configuration data as well a feature complete status interface that can be used as an alternative to nagios web interface.

Project website is at http://adagios.org

Live Demo
=========
http://demo.adagios.org/

Features
========
  - Full view/edit of hosts,services, etc
  - Tons of pre-bundled plugins and configuration templates
  - Network scan
  - Remote installation of linux/windows agents
  - Modern Status view as an alternative to default nagios web interface
  - Rest interface for status of hosts/services
  - Rest interface for viewing and modifying configuration
  - Full audit of any changes made

Design principals
==================
  - Useful for both novices and nagios experts
  - No database backend
  - Make common operational tasks as easy as possible
  - Assist Nagios admins in keeping configuration files clean and simple

Components
==========
  - Pynag - Nagios Configuration Parser
  - OKconfig - A robust plugin collection with preconfigured nagios template configuration files
  - PNP4Nagios - For Graphing Performance data
  - MK Livestatus - Broker module for nagios for high performance status information

Source Code
===========

	git clone http://github.com/opinkerfi/adagios.git

Install Instructions
====================
These installation instructions apply for rhel6. If running Fedora, please modify yum repos as needed.

For RHEL6/CentOS6 you must install epel yum repository (fedora users skip this step):

	rpm -Uvh http://download.fedoraproject.org/pub/epel/6/$HOSTTYPE/epel-release-6-8.noarch.rpm

Next step is to install OK yum repository:

	rpm -Uhv http://opensource.is/repo/ok-release-10-1.el6.noarch.rpm

Install needed packages:

	yum --enablerepo=ok-testing install -y nagios git adagios

Install okconfig (optional). Okconfig is a collection of plugins and templates for monitoring enterprise equipment. If installed Adagios will have options such as network scan and remote installation of clients.

	yum --enablerepo=ok-testing install -y okconfig

Adagios will not work unless you turn off selinux:

	sed -i "s/SELINUX=enforcing/SELINUX=permissive/" /etc/sysconfig/selinux
	setenforce 0

If you plan to access adagios through apache, make sure it is started:

	service httpd restart
	chkconfig httpd on


Same goes for nagios, start it if it is ready

	service nagios restart
	chkconfig nagios on
	

It is strongly recommended that you create a git repository in /etc/nagios/ and additionally give ownership of
everything in /etc/nagios to the nagios user.

	cd /etc/nagios/
	git init
	git add .
	git commit -a -m "Initial commit"
	# Make sure nagios group will always have write access to the configuration files:
	chown -R nagios /etc/nagios/* /etc/nagios/.git
	setfacl -R -m group:nagios:rwx /etc/nagios/
	setfacl -R -m d:group:nagios:rwx /etc/nagios/
	

By default objects created by adagios will go to /etc/nagios/adagios so make sure that this directory exists and 
nagios.cfg contains a reference to this directory.

	mkdir -p /etc/nagios/adagios
	pynag config --append cfg_dir=/etc/nagios/adagios

Congratulations! You are now ready to browse through adagios through http://$servername/adagios/. By default it
will use same authentication mechanism as nagios. (on rhel default is nagiosadmin/nagiosadmin and can be 
changed in /etc/nagios/passwd)

Using the Status view
=====================
Adagios has an experimental status view intended to partially replace the classical nagios web interface. If you want to try it out hen you need mk_livestatus and pnp4nagios broker modules installed:
	
	yum install -y pnp4nagios mk-livestatus --enablerepo=ok-testing
	pynag config --append "broker_module=/usr/lib64/nagios/brokers/npcdmod.o config_file=/etc/pnp4nagios/npcd.cfg"
	pynag config --append "broker_module=/usr/lib64/mk-livestatus/livestatus.o /var/spool/nagios/cmd/livestatus"
	pynag config --set "process_performance_data=1"
	
	# Add nagios to apache group so it has permissions to pnp4nagios's session files
	usermod -G apache nagios
	
	# We need to restart both apache and nagios so new changes take effect
	service nagios restart
	service httpd restart
	service npcd restart
	chkconfig npcd on

Contact us
===================
If you need any help with getting adagios to work, feel free to open up an issue on github issue tracker. If you want to chat you can contact us on:

  - Bug reports, feature requests: https://github.com/opinkerfi/adagios/issues
  - Mailing list: http://groups.google.com/group/adagios
  - IRC: #adagios on irc.freenode.net
