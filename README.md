# Kafka SMM Crash Course
## Agenda
- [Kafka Core APIs](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/README.md#kafka-has-four-core-apis)
- [Building blocks of Kafka](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/README.md#building-blocks-of-kafka)
- [Kafka Guarantees](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/README.md#kafka-guarantees)
- [Advance Kafka Topics](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/README.md#advance-kafka-topics)
- [Kafka Blindness](https://github.com/purn1mak/Kafka-SMM-CrashCourse/blob/master/README.md#kafka-blindness)
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

## Kafka Guarantees
At a high-level Kafka gives the following guarantees:

- Messages sent by a producer to a particular topic partition will be appended in the order they are sent. 
- A consumer instance sees records in the order they are stored in the log.
- For a topic with replication factor N, we will tolerate up to N-1 server failures without losing any records committed to the log.

## Advance Kafka Topics
- Idempotent producer
- Transactional API in Kafka for exactly once processing
- Authentication, authorization, 
- Replication
- Log compaction, compression
- Performance

## Kafka Blindness
### Kafka’s Omnipresence has led to the onset of “Kafka Blindness” 
- What is “Kafka Blindness”?\
  – Customers who use Kafka today struggle with monitoring / “seeing”/troubleshooting what is happening in their clusters
- Who is Affected?\
  –  Platform Operation Teams–Developers / DevOps Teams–Security / Governance Teams
- What are the Symptoms?\
  –  Difficulty seeing who is producing and consuming data\
  –  Difficulty understanding the flow of data from producers -> topics -> consumers\
  –  Difficulty troubleshooting/monitoring.

## Introduction to SMM
### Cure is Here: Clouderas Streams Messaging Manager (SMM)
- What is SMM?
  - New Open Source  project led by Cloudera to Cure the “Kafka Blindness”
  - Single Monitoring Dashboard for all your Kafka Clusters across 4 entities\
    – Broker\
    – Producer\
    – Topic\
    – Consumer\
- Designed for the Enterprise\
  – Support for Secure/Kerborized Kafka cluster\
  – Rich Access Control Policies (ACLS)\
  – Supports multiple HDP and/or HDF Kafka Clusters\
- REST as a First Class Citizen
- Delivered as a DataPlane Service
