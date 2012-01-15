
Molog : 

http://www.smetj.net/wiki/Molog

Build a scalable monitor and search solution for application and system logs with Nagios.

Molog is processing layer for a scalable logging infrastructure which consumes LogStash processed logs from RabbitMQ and sends updates to Nagios and ElasticSearch.

* A stand alone daemon with configurable parallel workers.
* Workers consume LogStash processed messages from RabbitMQ and perform ignore regex matching on them.
* Regex rules can be applied to all LogStash generated fields.
* Sends Nagios passive check results back to RabbitMQ.
* Nagios check results can be consumed from RabbitMQ into Nagios using Krolyk.
* Forwards and stores all messages to ElasticSearch.
* Only stores references to ElasticSearch records in a MongoDB instance.
* Provides REST API for querying and manipulating references and regexes.
* Includes molog_cli an interactive REST client to manipulate records, matches and regexes. 

MoLog is written in Python. 
