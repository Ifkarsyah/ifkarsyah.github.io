---
title: 1.2. Kafka History
type: docs
---

If you're in hurry, can skip this. Or, come back later.

## The Origins of Kafka in Linkedln

Kafka was developed around 2010 at LinkedIn by Jay Kreps, Jun Rao, and Neha Narkhede. The problem they originally set out to solve was to achieve low-latency ingestion of massive amounts of event data from the LinkedIn website activity(like page views, searches, or other actions) into a lambda architecture powered by Hadoop and real-time event processing technologies. 

The key was "real-time" processing. At the time, there were no solutions for this type of ingress in real-time systems. There were good solutions for ingesting data into offline batch systems, but they exposed implementation details to downstream users and used a push model that could easily overwhelm a consumer. Also, they were not designed for the real-time use case.

Real-time systems such as the traditional messaging queues (think ActiveMQ, RabbitMQ, etc.) have great delivery guarantees and support things such as transactions, protocol mediation, and message consumption tracking, but they are overkill for the use case LinkedIn had in mind.

## Replacing Traditional Message Broker

Over time, Kafka became popular as a more powerful alternative to older message brokers like RabbitMQ or ActiveMQ. So what does it do differently? Traditional brokers are great for decoupling data producers from consumers, buffering unprocessed messages, and letting systems process messages independently. The difference is:

- In **Kafka**, consumers pull data from a distributed log by requesting messages at their own pace. This allows consumers to control the rate of consumption and reprocess messages as needed, suiting high-throughput, event-streaming use cases where consumers may be at different offsets or need replay capabilities.

- In **RabbitMQ**, a traditional queue, the broker **pushes** messages to consumers as soon as they’re available. This push model prioritizes real-time message delivery, which is ideal for immediate processing and task-based workflows but doesn’t support message replay or as much control over consumption speed.

## Evolution of Kafka throughout the years

- **Initial Release (2011)**: Kafka was released as an open-source project by LinkedIn, establishing the core concepts of topics, producers, and consumers.
- **High Availability and Fault Tolerance (2012)**: Version 0.8 introduced replication and partitioning, enhancing fault tolerance and data redundancy.
- **Consumer Group Management (2014)**: Version 0.8.2 added support for consumer groups, allowing multiple consumers to share the processing load.
- **Streams API (2016)**: The introduction of the Kafka Streams API enabled real-time data processing applications directly on Kafka.
- **Transactional Messaging (2017)**: Version 0.11 introduced exactly-once semantics and transactions, ensuring data integrity across operations.
- **Schema Registry (2018)**: The Confluent Schema Registry was introduced for managing data schema evolution and compatibility.
- **Tiered Storage (2020)**: Added support for offloading older data to lower-cost storage solutions, improving disk usage and cost management.
- **Kubernetes Support (2020)**: Improved support for deploying and managing Kafka on Kubernetes environments.
- **KIP-500 (2021)**: A major architectural shift to eliminate ZooKeeper as a dependency, simplifying deployment and improving scalability.
- Performance Improvements (2021-Present): Ongoing updates focused on enhancing throughput, latency, and storage efficiency.
