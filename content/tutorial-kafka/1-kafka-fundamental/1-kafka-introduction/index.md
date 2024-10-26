---
title: 1.1. Kafka Introduction
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


## What

If you see from the official docs, it say:

> Apache Kafka is an open-source distributed **event streaming platform** used by thousands of companies for high-performance data pipelines, streaming analytics, data integration, and mission-critical applications.

What does it mean by Event Streaming Platform thought?

Event Streaming Platform means Kafka is designed to handle continuous streams of events (or messages) from multiple sources. An event here could be anything that happened within an application, such as a user click, a database update, or a device sending sensor data. Kafka captures, stores, and makes these events available in real-time to other systems that need to process them.

## Simplified Kafka Architecture

TBD: Simplified picture of Kafka architecture: 
many type of producer(service, OLTP db, IoT sensor data) -- topic in broker -- many type of consumer(other service, OLAP DB)

A Kafka cluster is composed of multiple brokers, which are the servers responsible for storing and managing data. Each broker contains topics, which are the streams or categories where messages are organized and stored.

Producers, such as various services, OLTP (Online Transaction Processing) databases with Change Data Capture (CDC), or IoT devices, generate events and send them to these topics. This setup allows for real-time data ingestion from diverse sources.

On the other side, consumers—which can be other services, OLAP (Online Analytical Processing) databases, or data analytics tools—read messages from the topics at their own pace. This separation of producers and consumers in a Kafka cluster enables efficient data processing and scalability, allowing multiple consumers to process data concurrently without affecting each other’s performance.

## Kafka Usecases

This is several usecase of Kafka.

### Website Activity Tracking

One of Kafka's earliest use cases at LinkedIn was building a user activity tracking pipeline based on real-time publish-subscribe feeds. Here’s how it works: website activity (like page views, searches, or other actions) is published to topics in Kafka, where each topic represents a specific type of activity. Various systems can subscribe to these topics for diverse purposes, such as:
- **Real-Time Processing**: Immediate analysis of user actions to enhance recommendations, personalization, or immediate responses to user behavior.
- **Real-Time Monitoring**: Continuous tracking for security alerts, anomaly detection, and monitoring site health.
- **Data Warehousing and Offline Analytics**: Activity data can also be streamed from Kafka into big data platforms like Hadoop or data warehouses for more intensive, offline analytics and reporting.


## Some confusion

### Is Kafka a traditional a message queue?

Kafka can indeed be used as a message queue, but it’s not a traditional message queue in the way systems like RabbitMQ or ActiveMQ operate. The difference lies in Kafka's design around log-based storage, and its ability to retain data. Kafka allows consumers to read messages at any point in time, whereas traditional message queues remove messages after they are read.

### Is Kafka a database?

Not really. Kafka is often described as a "event streaming platform" rather than a database. It stores streams of records, but it doesn’t provide features like SQL-based querying, strong transactional support, or a schema-enforced structure typical of databases. However, Kafka can persist data for a long time and allow replays, which can make it feel database-like.

What’s the difference between Kafka and a message queue?
Kafka is sometimes compared to traditional message queues like RabbitMQ. 

Ref: 
- https://everythingdevops.dev/is-apache-kafka-a-database
- https://www.kai-waehner.de/blog/2023/03/02/message-broker-and-apache-kafka-trade-offs-integration-migration/