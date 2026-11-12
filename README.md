# Vesta Blueprint 🧠

This repository contains the product specifications, UI/UX designs, and technical architecture for the Vesta Guest Experience Platform. 

It serves as the single source of truth for the system design before execution in the codebase, enabling a strict spec-driven development workflow.

## 📂 Documentation Index

### 1. Product Discovery (`/01-product-discovery`)
Defines the core problem, target audience, and business requirements.
* [The Problem Statement & Yercaud Case Study](./01-product-discovery/problem-statement.md)
* [User Personas](./01-product-discovery/user-personas.md)
* [MVP Scope & Requirements](./01-product-discovery/mvp-scope.md)

### 2. UI/UX Design (`/02-ui-ux-design`)
Maps the user journeys for both guests and resort staff.
* [Guest PWA Flows](./02-ui-ux-design/guest-flows.md)
* [Admin Dashboard Flows](./02-ui-ux-design/admin-flows.md)

### 3. High-Level Design (HLD) (`/03-architecture-hld`)
Outlines the distributed system architecture and core domains.
* [System Context & Architecture](./03-architecture-hld/system-context.md)
* [Domain Model](./03-architecture-hld/domain-model.md)
* [Architecture Decision Records (ADRs)](./03-architecture-hld/adrs)

### 4. Low-Level Design (LLD) (`/04-architecture-lld`)
Contains the technical contracts used to generate the application code.
* [Database Schema (PostgreSQL)](./04-architecture-lld/database-schema.md)
* [API REST Contracts](./04-architecture-lld/api-contracts.md)
* [Kafka Event Schemas](./04-architecture-lld/event-schemas.md)
