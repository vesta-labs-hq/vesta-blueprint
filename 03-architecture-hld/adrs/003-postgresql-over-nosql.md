# ADR 003: Use PostgreSQL for Core Persistence

## Context
We need a data store to handle resorts, guest profiles, activity schedules, and RSVPs.

## Decision
We will use **PostgreSQL**, a strict relational database, rather than a NoSQL document store (like MongoDB).

## Rationale
* **ACID Capacity Locks:** Activities have strict max capacities. PostgreSQL allows us to use row-level locking (`SELECT FOR UPDATE`) to prevent race conditions when two guests try to book the final spot simultaneously.
* **Multi-Tenancy Security:** By utilising composite foreign keys tied to a `resort_id`, we can enforce referential integrity at the database layer, making cross-tenant data leaks physically impossible.
* **Highly Relational Data:** The domain is inherently relational (Many Guests <-> Many Activities via RSVPs). Document stores would require messy data duplication and manual syncs to handle these relationships.
