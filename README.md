# Building-a-real-time-data-streaming-application-with-Apache-Kafka

## Introduction 

Real-Time Meetup RSPV Data Processing from https://www.meetup.com/. Real-Time Analytics using Apache Kafka, Zookeeper, PySpark. Analyzing the real time RSVP data of meetup.com to get real-time  such as trending topics, cities etc. along with other business insights related to Meetups RSVPs.

## Technologies Used

1. Kafka 2.8

2. Spark 2.4.5

3. Data Feeds: Kafka

4. ETL: Spark DataFrame, Spark Structured Streaming

5. Data Storage: Hdfs, S3

6. Resource Management: Yarn

7. Kafka Python API is used to interact with kafka cluster. PySpark is used to write the spark streaming jobs.


## Problem Statements

1. What are the current active cities in India which are scheduling Meetup Events?

2. What are the trending topics in US Meetup Events?

3. How many Big data Meetup Events events scheduled in Mumbai?


## Getting Started 

1. Assuming Kafka and Spark of appropriate version is installed, the following commands are used to run the application.
Spark Streaming integeration with kafka 0.10.0.0 and above, is still in experimental status, Hence using Kafka 0.9 (http://spark.apache.org/docs/latest/streaming-kafka-integration.html)

2. Run Zookeeper to maintain Kafka, command to be run from Kafka root dir bin/zookeeper-server-start.sh config/zookeeper.properties1

3. Start Kafka server, aditional servers can be added as per requirement. bin/kafka-server-start.sh config/server.properties

4. Start Producer.py to start reading data from the meetup stream and store it in '''meetup''' kafka topic.

5. Start Consumer.py to consume the stream from the '''meetup''' topic

6. Submit the spark job spark_meetup.py, to read the data into Spark Streaming from Kafka.

7. Spark depends on a external package for kafka integeration link

8. bin/spark-submit --packages org.apache.spark:spark-streaming-kafka-0-8_2.11:2.0.1 spark_meetup.py localhost:2181 meetup An analysis of number of RSVPs from various cities in "US" region is performed on the RSVPs Stream.
