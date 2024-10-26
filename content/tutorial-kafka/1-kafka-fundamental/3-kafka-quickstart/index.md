---
title: 1.3. Kafka Quickstart
summary: Everything you need to know about Kafka in 10 minutes
type: docs
---


https://kafka.apache.org/quickstart

## Exploring with Kafka CLI 

Kafka is a high-throughput, distributed messaging system that's widely used for building real-time streaming data pipelines. This guide covers a quickstart setup for Kafka with Docker Compose, focusing on the fundamentals: creating topics, producing messages, and consuming messages.


### Step 1: Set Up Kafka and Zookeeper with Docker Compose

> **Why learn with Docker Compose?** Using Docker Compose lets us focus on the functionality of Kafka without worrying about the underlying infrastructure setup. With a few lines of YAML configuration, we can have a multi-node Kafka cluster running locally and jump straight into exploring topics, producers, and consumers.

Create a `docker-compose.yml `file to set up Kafka and Zookeeper (Kafka requires Zookeeper for managing brokers).

```YAML
version: '3.7'

services:
  zookeeper:
    image: confluentinc/cp-zookeeper:7.7.1
    ports:
      - "2181:2181"
    environment:
      ZOOKEEPER_CLIENT_PORT: 2181
      ZOOKEEPER_TICK_TIME: 2000

  kafka-1:
    image: confluentinc/cp-kafka:7.7.1
    ports:
      - "9092:9092"
    environment:
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
      KAFKA_LISTENERS: INSIDE://0.0.0.0:9092
      KAFKA_ADVERTISED_LISTENERS: INSIDE://kafka-1:9092
      KAFKA_INTER_BROKER_LISTENER_NAME: INSIDE
      KAFKA_BROKER_ID: 1
      KAFKA_LOG_DIRS: /var/lib/kafka/data/broker-1
      KAFKA_REPLICATION_FACTOR: 1
      KAFKA_LISTENER_SECURITY_PROTOCOL_MAP: INSIDE:PLAINTEXT
    volumes:
      - kafka-1-data:/var/lib/kafka/data

  kafka-2:
    image: confluentinc/cp-kafka:7.7.1
    ports:
      - "9093:9093"
    environment:
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
      KAFKA_LISTENERS: INSIDE://0.0.0.0:9093
      KAFKA_ADVERTISED_LISTENERS: INSIDE://kafka-2:9093
      KAFKA_INTER_BROKER_LISTENER_NAME: INSIDE
      KAFKA_BROKER_ID: 2
      KAFKA_LOG_DIRS: /var/lib/kafka/data/broker-2
      KAFKA_REPLICATION_FACTOR: 1
      KAFKA_LISTENER_SECURITY_PROTOCOL_MAP: INSIDE:PLAINTEXT
    volumes:
      - kafka-2-data:/var/lib/kafka/data

  kafka-3:
    image: confluentinc/cp-kafka:7.7.1
    ports:
      - "9094:9094"
    environment:
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
      KAFKA_LISTENERS: INSIDE://0.0.0.0:9094
      KAFKA_ADVERTISED_LISTENERS: INSIDE://kafka-3:9094
      KAFKA_INTER_BROKER_LISTENER_NAME: INSIDE
      KAFKA_BROKER_ID: 3
      KAFKA_LOG_DIRS: /var/lib/kafka/data/broker-3
      KAFKA_REPLICATION_FACTOR: 1
      KAFKA_LISTENER_SECURITY_PROTOCOL_MAP: INSIDE:PLAINTEXT
    volumes:
      - kafka-3-data:/var/lib/kafka/data

volumes:
  kafka-1-data:
  kafka-2-data:
  kafka-3-data:
```

Start the services: `docker-compose up -d`

This command will launch Kafka and Zookeeper containers in detached mode.


### Step 2: Creating a Kafka Topic

Once the Kafka brokers are running, let’s create a topic called test-topic.
```YAML
docker exec -it kafka-1 \
  kafka-topics --create --topic test-topic \
  --bootstrap-server localhost:9092 \
  --partitions 1 --replication-factor 1
```

This command creates a new topic named `test-topic` with one partition and a replication factor of 1.
We will learn about this later.

To list all available topics, run:
```YAML
docker exec -it kafka-1 \
  kafka-topics --list \
  --bootstrap-server localhost:9092
```

### Step 3: Producing Messages to the Topic
To start a Kafka producer and write messages to `test-topic`:

```YAML
docker exec -it kafka-1 \
  kafka-console-producer \
  --topic test-topic --bootstrap-server localhost:9092
```
After the producer starts, type any message and press Enter. Each message you type will be sent to `test-topic`.


### Step 4: Consuming Messages from the Topic
In a new terminal, start a Kafka consumer to read from `test-topic`:
```
docker exec -it kafka-1 \
  kafka-console-consumer --topic test-topic \
  --bootstrap-server localhost:9092 --from-beginning
```
The consumer reads all messages from the beginning of `test-topic`. 
Put the 2 terminal side-by-side and see, each type yout type message in producer terminal, it will get printed in realtime in consumer terminal.

### Explanation
This quickstart demonstrates Kafka's basic commands to manage topics, produce, and consume messages using the Kafka CLI. However, you rarely do this in real environment. Instead, a declarative approach is often preferred for topic management, and applications typically handle producing and consuming messages in the code using a language-specific Kafka client (e.g., Python, Go, Java).

So, keep continue reading.

## Creating Topic Declaratively

In production, Kafka topics can be managed using declarative tools for better automation. Two common approaches are:

1. **Terraform**: Use the Terraform Kafka provider to manage topics as code.
2. **Kubernetes Operator**: Kafka operators like Strimzi or Confluent Operator enable Kubernetes-native topic management, scaling, and other cluster operations.

Example Terraform configuration for creating a Kafka topic:
```YAML
resource "kafka_topic" "example" {
  name               = "user-events"
  partitions         = 3
  replication_factor = 2
  config = {
    "retention.ms" = "604800000"  # 7 days
  }
}
```

## Producing and Consuming Message with Code

In many setups, backend applications are commonly built in Golang for its performance and concurrency support, while machine learning applications often use Python due to its extensive ML library support.

Let’s create an example where a Golang application produces messages to a `user` topic, while a Python application consumes these messages and detect if the `user' age` is unsual.

### Golang Producer: Sending User Information

The Golang producer sends user information (`{name: "Alice", age: 30}`) to the `user` topic.

```go
package main

import (
    "context"
    "fmt"
    "github.com/segmentio/kafka-go"
    "log"
)

func main() {
    writer := kafka.NewWriter(kafka.WriterConfig{
        Brokers: []string{"localhost:9092"},
        Topic:   "user",
    })
    defer writer.Close()

    message := kafka.Message{
        Key:   []byte("user_1"),
        Value: []byte(`{"name": "Alice", "age": 30}`),
    }
    err := writer.WriteMessages(context.Background(), message)
    if err != nil {
        log.Fatalf("could not write message %v", err)
    }
    fmt.Println("Message sent to topic 'user'")
}
```

### Python Consumer: Detecting Unusual Ages

The Python consumer reads messages from the user topic and checks if the age field is above 130, logging it as "unusual".

```python
from kafka import KafkaConsumer
import json

consumer = KafkaConsumer(
    'user',
    bootstrap_servers='localhost:9092',
    auto_offset_reset='earliest',
    value_deserializer=lambda m: json.loads(m.decode('utf-8'))
)

for message in consumer:
    user = message.value
    if user['age'] > 130:
        print(f"Unusual age detected: {user['age']} for user {user['name']}")
    else:
        print(f"User data received: {user}")
```

In a real system, these applications would run on separate servers or within different containers, each handling a part of the data flow.


## Next Reading