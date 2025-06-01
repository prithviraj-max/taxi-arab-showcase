# 🚖 Ride Cycle Logic – Taxi Arab

This document summarizes the logic of assigning rides to drivers using batch invitations and Laravel Queues.

---

## 🔁 Flow Overview

1. **Customer Requests Ride**
   - System checks nearby available drivers
   - Filters based on location, car type, and online status
   - Drivers already invited to other rides are excluded
   - Female vs All ride types determine available car types

2. **Driver Invitation Logic**
   - A batch of 3 drivers is selected (configurable via `$limit` parameter)
   - Selection based on proximity using haversine formula for distance calculation
   - Invitations are sent in parallel with identical expiry times
   - Each driver gets a timeout window to respond (configured in settings via `INVITE_EXPIRY_TIMEOUT`)

3. **Handling Responses**
   - If a driver **accepts**, the ride is assigned and all other pending invitations are expired
   - If another driver tries to accept after, they receive "ride already accepted" message
   - If **all drivers decline**, a new batch is immediately selected
   - If **some drivers decline** but others haven't responded, system waits until timeout
   - If **no drivers accept at all** after max retries, ride is canceled with "maximum attempts exceeded"

---

## 👨‍💻 Tech Behind It

- Queues handled by **Redis**
- Job logic inside `SearchForDriverJob` with batched invitation processing
- Driver discovery in `RideInviteService::getClosestDriversToRide()`
- Invitation management in `RideInviteService::sendInvite()`
- Acceptance handling in `RideAcceptService::accept()`  
- Real-time notifications via **Pusher**
- Status stored in DB with full logs for each invite batch

---

## 🛡️ Concurrency & Race Conditions

- Multiple drivers can receive invitations simultaneously
- First driver to accept gets the ride via database transaction locking
- All other invitations are immediately expired on successful acceptance
- Delayed jobs are canceled if a ride is accepted/canceled to prevent duplicates

---

## ✅ Admin Dashboard Monitoring

- Max retries shown in settings (`MAX_DRIVER_SEARCH_RETRIES`)
- Invitation batch size configurable in code (`$limit` parameter)
- All ride status transitions are logged with timestamps
- Complete invitation history viewable for troubleshooting
- Agents can view driver responses, cancel, or reassign manually

---

## 🧠 Technical Notes

- System prevents duplicate invitations using a combination of:
  - Database constraints
  - Job queuing with unique ride IDs
  - Explicit checking before sending invites
- Invitation expiry is handled by the job scheduler based on the latest invitation expiry time
- Debug logging captures both individual and batch invitation metrics
- Female ride type allows access to all car types, while All type restricts to non-female-designated cars
