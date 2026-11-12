# ADR 004: Use RabbitMQ instead of Apache Kafka

## Context
The system needs an event broker to handle asynchronous tasks, specifically routing real-time push notifications and offer broadcasts without blocking the main API threads.

## Decision
We will use **RabbitMQ** as our message broker instead of Apache Kafka.

## Rationale
* **Fire-and-Forget Routing:** Vesta needs to deliver a notification to a queue, route it to a worker, send it to the guest, and drop it. We do not need Kafka’s core feature of permanent event log retention and replayability.
* **Lightweight Footprint:** RabbitMQ consumes a fraction of the CPU and memory resources compared to a Kafka cluster (which requires Zookeeper/KRaft). This keeps our cloud infrastructure costs significantly lower for the MVP.
* **Simplicity:** RabbitMQ’s exchange/queue routing model perfectly fits our need to route specific notifications to specific resort channels with minimal configuration overhead.
