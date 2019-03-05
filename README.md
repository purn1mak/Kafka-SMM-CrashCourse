# Kafka SMM Crash Course
## Agenda
- [Kafka Core APIs]()
- Building blocks of Kafka
- Kafka Guarantees
- Kafka Blindness
- Introduction to SMM
  - SMM REST SERVICES
  - SMM INTEGRATION WITH 
    - APACHE ATLAS
    - APACHE AMBARI
    - APACHE RANGER
    - SCHEMA REGISTRY
    - GRAFANA
- Topic Lifecycle Management
- Alerting
- Schema Registry Integration
- KStreams
- Hive + Kafka

## Kafka has four core APIs:

- The [Producer API](https://kafka.apache.org/documentation.html#producerapi) allows an application to publish a stream of records to one or more Kafka topics.
- The [Consumer API](https://kafka.apache.org/documentation.html#consumerapi) allows an application to subscribe to one or more topics and process the stream of records produced to them.
- The [Streams API](https://kafka.apache.org/documentation/streams/) allows an application to act as a stream processor, consuming an input stream from one or more topics and producing an output stream to one or more output topics, effectively transforming the input streams to output streams.
- The [Connector API](https://kafka.apache.org/documentation.html#connect) allows building and running reusable producers or consumers that connect Kafka topics to existing applications or data systems. For example, a connector to a relational database might capture every change to a table.
![Image](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/KafkaBasic.png)


## **Building Blocks of Kafka**
- **Producer:** A publisher of messages to 1 or more topics. Sends data to brokers.
- **Topics:** A stream of messages belonging to a category, which are split into partitions. A topic must have at least one partition.
- **Partition:** Has messages in an immutable sequence and are implemented as segment files of equal sizes. They can also handle an arbitrary amount of data.
- **Partition Offset:** A unique sequence ID from partition message.
- **Replicas of Partition:** A “Backup” of a partition. They never read or write data and they prevent data loss.
- **Kafka Brokers:** Responsibility is to maintain published data.
- **Lead Broker:** Node responsible for all Read or Write performed on a given partition.
- **Follower Broker:** Node that follows the leaders instructions. It will take the place of the leader if the leader fails. Also pulls in messages like a consumer and updates its data store.
- **Kafka Cluster:** Kafka is considered a Kafka Cluster when more than one broker exist. The main reason for having multiple brokers is to manage persistance and replication of message data and expand without downtown.
- **Consumer Group:** Consumers that come from the same group ID.
- **Consumers:** Read data from brokers by pulling in the data. They subscribe to 1 ore more topics.
![Image](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/KafkaWhiteBoarding.png)
