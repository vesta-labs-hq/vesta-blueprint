# Guest User Journeys (PWA)

## Flow 1: Frictionless Onboarding & Discovery
1. **Trigger:** Guest scans QR code in their room or at the reception.
2. **Action:** Browser opens the React PWA. No app store download required.
3. **Authentication:** Guest enters Room Number and Last Name (Lightweight Auth).
4. **Result:** Lands on the `Daily Itinerary Feed` showing today's timeline of events.

## Flow 2: RSVP & Contextual Upsell
1. **Trigger:** Guest taps "Coffee Plantation Walk" on the itinerary.
2. **Action:** Views details (time, meeting point, capacity). Taps "RSVP for 2".
3. **Result:** Spot is secured. 
4. **The Upsell:** A contextual toast appears: *"Since you're walking early, grab a coffee! 15% off at the Cafe before 9 AM."*

## Flow 3: Real-Time Updates
1. **Trigger:** Rain starts; Admin delays the walk by 30 minutes.
2. **Action:** Guest receives a web push notification (or in-app alert if currently browsing).
3. **Result:** Guest stays in their room, avoiding frustration and front-desk queuing.
