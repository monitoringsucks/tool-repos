Critical is my take on network/infrastructure monitoring. Here are the big
ideas:

* Infrastructure as code: The monitoring system should be an internal DSL so it
  can natively interact with any part of your infrastructure you can find or
  write a library for. You should also be able to productively alter its guts if
  you need to. This is a monitoring system for ops people who write code and
  coders who do ops.
* Client-based: This scales better, and is actually easier to configure if you
  use configuration management, which you should be doing anyway.
* Continuous verification: Critical has a single shot mode in
  addition to the typical daemonized operation. This allows you to verify the
  configuration on a host after making changes and then continuously monitor the
  state of the system using the same verification tests.
* Declarative: Declare what the state of your system is supposed to be.
* Alerting and Trending together: a client/agent can do both of these at the
  same time with less configuration overhead. It makes sense to keep them
  separate on the server side.
* Licensing: "Do what thou wilt shall be the whole of the law," except for
  patent trolls, etc. So, Apache 2.0 it is.
  
https://github.com/danielsdeleo/critical