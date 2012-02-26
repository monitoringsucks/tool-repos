[link](https://github.com/Netflix/servo/wiki)

The goal of Servo is to provide a simple interface for exposing and publishing application metrics in Java.

The primary requirements are:

+ **Leverage JMX**: JMX is the standard monitoring interface for Java and can be queried by many existing tools.
+ **Keep it simple**: It should be trivial to expose metrics and publish metrics without having to write lots of code such as "MBean interfaces":http://docs.oracle.com/javase/tutorial/jmx/mbeans/standard.html.
+ **Flexible publishing**: Once metrics are exposed, it should be easy to regularly poll the metrics and make them available for internal reporting systems, logs, and services like "Amazon's CloudWatch":http://aws.amazon.com/cloudwatch/.
