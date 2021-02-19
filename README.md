# Kafka-Installation steps
## Download the latest [Kafka](https://www.apache.org/dyn/closer.cgi?path=/kafka/2.7.0/kafka_2.13-2.7.0.tgz) release and extract it:
Open the Bash in the C folder and run the following commands.
1. $ tar -xzf kafka_2.13-2.7.0.tgz
2. cd kafka_2.13-2.7.0

# Kafka Commands
1. Window 1 - Run Zookeeper Service  (keep window open)
   .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

2. Window 2 - Run Kafka Service (keep window open)
   \bin\windows\kafka-server-start.bat .\config\server.properties

3. Window 3 (temporary) - Execute One-Time Commands - create, list, delete topics 
   .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic bearcat-messages
   .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list

4. Window 4 - Run Kafka Producer (will provide a > prompt for writing messages)
   .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic tourism

5. Window 5 - Run Kafka Consumer (to show messages from the beginning)
   .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic tourism --from-beginning
