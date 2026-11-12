# ADR 001: Use Hexagonal Architecture (Ports and Adapters)

## Context
As a B2B SaaS, Vesta's core business logic (Scheduling, Tenancy, Offers) is complex and must be fiercely protected from framework changes, database migrations, or third-party API swaps. 

## Decision
We will use **Hexagonal Architecture** for the Spring Boot API. 
* **Domain Layer:** Pure Java. No Spring annotations. Contains all business rules.
* **Ports:** Interfaces defining how the domain communicates with the outside world (e.g., `ActivityRepository`, `NotificationPublisher`).
* **Adapters:** Spring Controllers (Web Adapter), Spring Data JPA (Persistence Adapter), Kafka Producers (Event Adapter).

## Consequences
* **Pros:** Business logic is 100% unit-testable without booting up the Spring context. We can swap PostgreSQL for MySQL, or Kafka for RabbitMQ, by only changing one adapter file.
* **Cons:** Introduces slightly more boilerplate code (mapping between Domain entities and JPA entities). Worth the trade-off for long-term maintainability.
