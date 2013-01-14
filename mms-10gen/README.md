MongoDB Monitoring Service (MMS)

MongoDB Monitoring Service (MMS) is a free cloud-based service provided by 10gen for monitoring MongoDB deployments in real time. MMS features charts, custom dashboards and automated alerting to track performance, utilization and other KPIs. It requires minimal setup and configuration, and within minutes devops and sysadmin teams can manage and optimize MongoDB deployments.

Proactive Monitoring and Management



MMS collects statistics on all key server and hardware indicators and presents the data in a powerful web console. MMS tracks over 100 metrics to monitor the health of MongoDB clusters. By default, the MMS dashboard displays 9 metrics:

Op Counters – Count of operations executed per second
Memory – Amount of data MongoDB is using
Lock Percent – Percent of time spent in write lock
Background Flush – Average time to flush data to disk
Connections – Number of current open connections to MongoDB
Queues – Number of operations waiting to run
Page Faults – Number of page faults to disk
Replication – Oplog length (for primary) and replication delay to primary (on secondary)
Journal – Amount of data written to journal
Designed specifically for MongoDB, MMS ensures that users have visibility into the right metrics to optimize applications during development and in production. With sharded clusters comprising dozens of nodes, MMS provides a holistic view of entire MongoDB deployments.

For customers with MongoDB Subscriptions, MMS enables 10gen engineers to monitor deployments on an ongoing basis and suggest corrective action before degradation occurs. MMS also helps shorten the response time for commercial support issues. When customers file tickets with the 10gen support team, our engineers can examine their MMS data, enabling them to identify customers' system configurations and any troubling signs about their clusters.

Easy Setup

Setting up MMS is simple:

Create an account at mms.10gen.com.
Download and install the MMS agent on your cluster.
Within minutes, a dashboard of your cluster will be available on mms.10gen.com.
No administration or maintenance is required.
