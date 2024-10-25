---
title: 1.1. Kafka History and Introduction
summary: Everything you need to know about Kafka in 10 minutes
date: 2024-01-17
type: docs
math: false
---

## TLDR
- **Kafka History**: Explain how Kafka was created at LinkedIn by Jay Kreps, Neha Narkhede, and Jun Rao. Discuss what they are trying to solvo so that thay build kafka.
  - https://www.frontier-enterprise.com/unleashing-kafka-insights-from-confluent-jun-rao/
  - https://www.linkedin.com/pulse/kafkas-origin-story-linkedin-tanvir-ahmed/
- **Do you need to learn Kafka**: If you read this article, means probably yes.
  - **Increased Job Opportunities**: Many companies seek software engineers with experience in Kafka, especially in industries focused on big data, fintech, e-commerce, and real-time analytics. Understanding Kafka can make you a more attractive candidate for such positions.
  - **Microservices Architecture**: If you work with microservices, Kafka can be invaluable for managing communication between services. It helps decouple services and enables them to communicate asynchronously, making your applications more scalable and resilient.
- **Do your company need Kafka**: 




## History

### The Origins of Kafka

Kafka was developed around 2010 at LinkedIn by Jay Kreps, Jun Rao, and Neha Narkhede. The problem they originally set out to solve was to achieve low-latency ingestion of massive amounts of event data from the LinkedIn website and infrastructure into a lambda architecture powered by Hadoop and real-time event processing technologies. The key was "real-time" processing. At the time, there were no solutions for this type of ingress in real-time systems.

There were good solutions for ingesting data into offline batch systems, but they exposed implementation details to downstream users and used a push model that could easily overwhelm a consumer. Also, they were not designed for the real-time use case.

Real-time systems such as the traditional messaging queues (think ActiveMQ, RabbitMQ, etc.) have great delivery guarantees and support things such as transactions, protocol mediation, and message consumption tracking, but they are overkill for the use case LinkedIn had in mind.

### The Birth of Apache Kafka

After months of development and iteration, the team unveiled their creation: Apache Kafka. Released as an open-source project in 2011, Kafka revolutionized the way organizations handled streaming data. At its core was a distributed commit log, which provided a durable and fault-tolerant foundation for real-time event processing.

## Should You Have Kafka? Or, Do You Have the same problem as LinkedIn?

Before jumping on the Kafka bandwagon, it’s essential to ask if your organization truly needs a system like Kafka or if you're simply captivated by its buzz. The fundamental question boils down to this: do you have the same problem as Linkedln? 

Kafka was designed to handle high-throughput, low-latency data streams with a durable, distributed, and scalable foundation. But, if your data needs don’t align with those requirements, Kafka might be overkill.

### When Kafka Might Be Overkill

#### Low to Moderate Data Volume

If you’re not dealing with thousands of events per second, Kafka’s setup may be more than you need. A simpler message broker like RabbitMQ or Redis Pub/Sub, or even a managed queue like AWS SQS or Google Pub/Sub, could handle smaller loads with less maintenance.

#### Lighter Data Pipeline Needs
If you’re only looking to relay a small number of events between services or you don’t need long-term durability (i.e., storing events for days or months), Kafka’s persistence capabilities may be unnecessary.

#### Limited Infrastructure Resources
Kafka requires substantial setup and ongoing maintenance, including managing a cluster of brokers and monitoring. This can strain a small engineering team.

### When Kafka Could Be Beneficial

#### Real-Time Streaming Requirements
If your application requires real-time processing (e.g., recommendation engines, fraud detection, or real-time analytics), Kafka is a strong option due to its high throughput and low latency.

#### Event-Driven Microservices Architecture
If your product is heavily event-driven with multiple services that need to publish and subscribe to events, Kafka can help efficiently manage and scale these interactions, especially if you're planning to scale in the near future.

#### Data Integration Across Systems
Kafka shines in scenarios where you need to stream data from multiple sources to different sinks (e.g., databases, storage systems, other applications). This is especially true with Kafka Connect, which supports integrations with numerous data systems.

#### Growth Plans for Scale
If you anticipate substantial growth in data volume or complexity, investing in Kafka early could save migration time and effort later.


### How would You Introduce Kafka Incrementally?
- https://streamnative.io/blog/a-guide-to-evaluating-the-infrastructure-costs-of-apache-pulsar-and-apache-kafka


