
[github](https://github.com/zealot2007/redis-cluster-monitor)

Perhaps not ready for primetime, but for your consideration, this project's readme:

---

UPDATE: please note that this is just a toy. A proper "redis-cluster" is on the
official Redis roadmap.  There's also the [twine
project](http://github.com/alexgenaud/twine) to consider.

---

Redis supports master-slave (1:N) replication but does not support *automatic*
failover. That is, if the master "goes down" for any reason, your sysadmin
(read: you) has to reconfigure one of the Redis slaves to be the new master.

One could use monit or God or whatever alongside redis-cli to check if a host is
up, then send the other hosts a SLAVEOF command to reconfigure the cluster
around a new master.

I created a Python script that does this instead. It only took an hour to do so
no big loss. OK, I didn't think of using redis-cli initially :)

Perhaps this project could at least be a part of the infrastructure (perhaps in
concept only) for the forthcoming "redis-cluster" project.

The [original mailing list thread](http://groups.google.com/group/redis-db/browse_thread/thread/497ee813c9960a50)
discusses the origins of this project a bit.

