# System Context & Architecture

Vesta follows a decoupled, distributed microservices approach optimized for multi-tenancy and lightweight real-time updates.

## High-Level Architecture Diagram

[ Guest (React PWA) ]           [ Admin (React Dashboard) ]
         |                                  |
         | (HTTPS / SSE)                    | (HTTPS)
         v                                  v
+---------------------------------------------------------+
|                Vesta Core API (Spring Boot)             |
|                                                         |
|  [ Auth/Tenancy ] [ Scheduling ] [ Offers ] [ RSVPs ]   |
+---------------------------------------------------------+
         |                                  |
         v                                  v
[ PostgreSQL (Data Store) ]       [ RabbitMQ (Message Broker) ]
   - Multi-tenant schemas            - Async Task Routing
   - Strict Relational Integrity     - Push Notification Queues
   - ACID Capacity Locks
