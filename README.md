Instructions to run Kafka/zookeeper locally:
--------------------------------------------

Followed steps from here for a windows installation:
https://dzone.com/articles/running-apache-kafka-on-windows-os

Kafka CheatSheet:
-----------------
https://ronnieroller.com/kafka/cheat-sheet#list-topics


KafkaTool:
----------
KafkaTool is a GUI tool to view Kafka brokers, topics, and data on the topics:

http://www.kafkatool.com/download.html

Quick Start:
------------
-- assuming JDK/JRE pre-reqs are met already

Start Zookeeper:
----------------
Installed at:  C:\madhu\tools\zookeeper-3.5.4-beta

running:
cd C:\madhu\tools\zookeeper-3.5.4-beta\bin\
zkServer.cmd

(should use the default config file conf\zoo.cfg)

Should have zookeeper running on default port 2181 (on localhost).

Start Kafka Server:
-------------------
C:\madhu\tools\kafka_2.12-2.1.0>bin\windows\kafka-server-start.bat config\server.properties
 
Create Kafka Topic:
-------------------
C:\madhu\tools\kafka_2.12-2.1.0>bin\windows\kafka-topics.bat --zookeeper localhost:2181 --create --replication-factor 1 --partitions 1 --topic analytics-bus

List topics:
 
C:\madhu\tools\kafka_2.12-2.1.0>bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list

Start Kafka Producer CLI:
-------------------------
C:\madhu\tools\kafka_2.12-2.1.0>bin\windows\kafka-console-producer.bat --broker-
list localhost:9092 --topic analytics-bus

Shows a > prompt where you can enter text messages that will get put on the given topic "analytics-bus"


Start Kafka Consumer CLI:
-------------------------

C:\madhu\tools\kafka_2.12-2.1.0>bin\windows\kafka-console-consumer.bat --bootstr
ap-server localhost:9092 --topic analytics-bus

Note: It doesn't show any prompt once it starts!

Now send a few messages from producer, see them appear on the consumer window! Also see them in the Kafka Tool. Hex format.
