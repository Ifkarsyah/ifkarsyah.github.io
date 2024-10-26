---
title: 1.5. Kafka Producer and Consumer
summary: Learn how to produce (write) messages to topics and consume (read) them effectively.
type: docs
---
## Oret

Explore how messages are structured, including key-value pairs and the use of serialization formats like JSON, Avro, or Protobuf.

At-Least-Once, At-Most-Once, Exactly-Once: Explore the different delivery guarantees Kafka offers and how to implement them in your applications.


## Kafka Producers

Once a topic has been created with Kafka, the next step is to send data into the topic. This is where Kafka Producers come in.

A Kafka producer sends messages to a topic, and messages are distributed to partitions according to a mechanism such as key hashing (more on it below).

For a message to be successfully written into a Kafka topic, a producer must specify a level of acknowledgment (acks). This subject will be introduced in depth in the topic replication section.


