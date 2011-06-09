OpenTSDB is a distributed, scalable Time Series Database (TSDB) written on 
top of HBase. OpenTSDB was written to address a common need: store, index
and serve metrics collected from computer systems (network gear, 
operating systems, applications) at a large scale, and make this data 
easily accessible and graphable.

Thanks to HBase's scalability, OpenTSDB allows you to collect many thousands
of metrics from thousands of hosts and applications, at a high rate  (every 
few seconds). OpenTSDB will never delete or downsample data and can easily 
store billions of data points. As a matter of fact, StumbleUpon uses it to 
keep track of hundred of thousands of time series and collects over 
100 million data points per day in their main production cluster.

http://opentsdb.net/
