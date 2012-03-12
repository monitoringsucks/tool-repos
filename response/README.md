Response - Monitoring doesn't have to suck.

Response is an simple Graphite proxy with plugable alerting support. It's first priority is to deliver messages to Graphite rapidly. In the event that Graphite goes down, messages will be buffered until Graphite is back. Eventually Redis will be optionally supported to provide arbitrary levels of durability/persistence 


https://github.com/gflarity/response
