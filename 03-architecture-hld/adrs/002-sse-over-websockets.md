# ADR 002: Use Server-Sent Events (SSE) instead of WebSockets

## Context
The Guest PWA and Admin Dashboard require real-time updates for schedule changes, rain delays, and flash offers. 

## Decision
We will use **Server-Sent Events (SSE)** over standard HTTP instead of WebSockets.

## Rationale
* **Unidirectional Data Flow:** Resort updates are exclusively Server-to-Client broadcasts. Clients do not need to stream data back to the server continuously.
* **Lower Overhead:** WebSockets maintain heavy, persistent TCP connections which are difficult to load balance and consume excess memory. SSE operates over standard HTTP, making it vastly lighter, easier to cache, and naturally supported by modern browsers.
* **State Management:** When a guest acts (e.g., RSVPs), standard stateless HTTP POST requests are sufficient and simpler to secure.
