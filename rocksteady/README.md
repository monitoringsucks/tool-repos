Rocksteady is a java application that reads metrics from RabbitMQ, parse them and turn them into events so Esper(CEP) can query against those metric and react to events match by the query.

Rocksteady is an effort to utilize complex event process engine to analyze user defined metric. End goal is to derive root cause conclusion based on metric driven events. Rocksteady is only the metric analysis part of the whole picture, but we also present a solution including metric convention, metric sending, load balancing, and graphing that work well for us.

http://code.google.com/p/rocksteady/
