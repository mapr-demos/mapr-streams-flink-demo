# Apache Flink and MapR Streams

This project is use a simple Flink job to show how to integrate MapR Streams to Flink using the Flink Connector for Kafka.


## Configure MapR Streams

Create a MapR Stream and Topic

```
$ maprcli stream create -path /apps/application-stream -produceperm p -consumeperm p -topicperm p
$ maprcli stream topic create -path /apps/application-stream -topic flink-demo 
```

## Build and Run the Application

In the project folder:

```
$ mvn clean package 
```

And run the Flink Consumer:

```
$ mvn exec:java -Dexec.mainClass=com.mapr.demos.ReadFromKafka
```

and Producer: 

```
$ mvn exec:java -Dexec.mainClass=com.mapr.demos.WriteToKafka
```

You should see messages printed in the Consumer console.

You can run this application directly in a Flink cluster.

