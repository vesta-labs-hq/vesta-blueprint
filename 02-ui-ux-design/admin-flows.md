# Admin Dashboard User Journeys

## Flow 1: Event Orchestration
1. **Trigger:** Front desk staff logs into the React Admin Dashboard.
2. **Action:** Navigates to `Schedule Manager`. Clicks "New Activity".
3. **Input:** Enters Title (Magic Show), Time, Location, and Max Capacity (50).
4. **Result:** Activity instantly populates on all Guest PWAs.

## Flow 2: Emergency / Update Broadcast
1. **Trigger:** The Magic Show location changes from the Lawn to the Banquet Hall.
2. **Action:** Admin opens the specific activity in the dashboard.
3. **Input:** Updates the location field and clicks "Broadcast Update".
4. **Result:** The system triggers an instant push notification to *only* the guests who RSVP'd.

## Flow 3: Offer Deployment
1. **Trigger:** The spa is empty this afternoon; Manager wants to drive revenue.
2. **Action:** Navigates to `Offers Engine`. Clicks "Create Flash Offer".
3. **Input:** Creates "20% off Couple's Massage - Today Only". 
4. **Result:** Offer appears at the top of the Guest PWA feed as a featured card.
