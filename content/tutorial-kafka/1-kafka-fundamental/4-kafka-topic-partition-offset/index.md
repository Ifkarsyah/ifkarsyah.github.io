---
title: 1.4. Kafka Topic and Partition
summary: Understand how topics are used to categorize messages and how partitions allow for scalability and parallelism.
type: docs
---

## Topic

Kafka **topics** organize related events. For example, we may have a topic called logs, which contains logs from an application. Topics are roughly analogous to SQL tables. However, unlike SQL tables, Kafka topics are not queryable. Instead, we must create Kafka producers and consumers to utilize the data. 

Kafka topics can contain any kind of message in any format, and the sequence of all these messages is called a data stream.

Data in Kafka topics is deleted after one week by default (also called the default message retention period), and this value is configurable. This mechanism of deleting old data ensures a Kafka cluster does not run out of disk space by recycling topics over time.

## Partition

Topics are broken down into a number of partitions. 

The number of partitions of a topic is specified at the time of topic creation. Partitions are numbered starting from `0` to`N-1`, where `N` is the number of partitions. The figure below shows a topic with three partitions, with messages being appended to the end of each one.

## Offset 
The offset is an integer value that Kafka adds to each message as it is written into a partition. Each message in a given partition has a unique offset.

## Producer
https://learn.conduktor.io/kafka/kafka-producers/

## Consumer

https://learn.conduktor.io/kafka/kafka-consumers/