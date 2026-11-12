# Domain-Driven Design (DDD) Bounded Contexts

To keep the codebase clean, Vesta's Core API is divided into strict bounded contexts.

## 1. Tenancy & Identity Context
* **Responsibility:** Manages the Resorts (Tenants) and Guest Sessions.
* **Entities:** `Resort`, `GuestProfile`, `Session`.
* **Rules:** Every API request must pass through a tenant filter. Guests are scoped to a specific `ResortId`.

## 2. Event Orchestration Context
* **Responsibility:** The core scheduling engine.
* **Entities:** `Activity`, `Schedule`, `Location`.
* **Rules:** Handles capacity limits, time conflicts, and status changes (e.g., Active -> Delayed -> Cancelled).

## 3. RSVP & Engagement Context
* **Responsibility:** Tracks guest participation.
* **Entities:** `RSVP`, `Feedback`.
* **Rules:** Guests can only RSVP if capacity > 0. Triggers a Kafka event upon successful RSVP.

## 4. Offers & Upsell Context
* **Responsibility:** Manages revenue-driving promotions.
* **Entities:** `Offer`, `Redemption`.
* **Rules:** Evaluates rules (e.g., "Only show to Guests with an RSVP to Activity X") before displaying on the PWA.
