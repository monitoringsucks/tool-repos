## About

This is a [Gearman](http://gearman.org/) Worker that is designed to use the nagios performance data generated and published by the awesome Nagios-Plugin [Mod-Gearman](http://mod-gearman.org/) and feed them into [Graphite](http://graphite.wikidot.com/) or anything that understands one of the Graphite-Protocols.

Since it is a worker you can scale it as you like by using a larger pool (processes that are spawned on the machine running the graphiteworker) or by starting it on a many machines as you like. It only opens one connection to graphite and sends all data arriving in Germans perfdata queue. You can choose if you want to use the line or the pickle protocol. Since graphite works best with the line protocol I suggest you to use it to feed your data.

[link](https://github.com/Crapworks/graphiteworker)
