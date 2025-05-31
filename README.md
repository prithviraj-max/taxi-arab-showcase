# 🚕 Taxi Arab – Laravel Backend Contributions

> 💼 This is a **work showcase repo** for my contributions as a backend developer on a real ride-hailing app built with Laravel.

---

## 🧠 About the App

**Taxi Arab** is a live ride-hailing app similar to Uber, operating in Jordan 🇯🇴 with real users, real drivers, and real-time orders.

It has separate mobile apps for **customers** and **drivers**, and the backend is a Laravel system I worked on extensively to **improve its core logic, scalability, and reliability**.

---

## 🧑‍💻 My Role

- **Position**: Backend Developer (Laravel)
- **Period**: Jan 2025 – Present
- **Team**:
  - Myself (Laravel backend)
  - Ali (iOS developer)
  - Kareem (Android developer)

---

## 🚀 What I Did

### ✅ Rebuilt the Ride Invitation Logic

- Completely rewrote the **driver assignment cycle**
- Switched from 1-by-1 to **3-by-3 batch invitations**
- Made retry count dynamic using a `MAX_RETRY_COUNT` setting in the DB
- Added logic to auto-cancel invites when they reach the limit

### ✅ Queues & Job Optimization

- Used **Redis** as `queue` driver for better scalability
- Optimized job dispatching using `dispatch($rideId)` over model binding
- Prevented duplicate queue jobs and stopped jobs immediately when needed
- Refactored `SearchForDriverJob` and added `cancelQueuedJob()` method

### ✅ Agent/Driver Presence Logic

- Implemented **online/offline driver system**
- Added `is_online` field to the drivers table
- Excluded offline drivers from receiving ride invitations
- Suggested & applied production-safe solution to reset driver tokens

### ✅ Admin Dashboard Enhancements

- Built **real-time stats tracking** for dashboard
- Improved ride analytics by filtering out non-accepted rides
- Added **export to Excel** for driver phone numbers
- Added `acceptance_status` filters for ride reports

### ✅ Production-Level Debugging & Deployment

- Debugged live ride flow on production safely with `info()` logs
- Performed all deployments **after midnight** to avoid user interruption
- Maintained stability during updates to queue workers, logic & database

---

## 📊 Real-Time Chat & Notifications

- Used **Pusher** for real-time ride updates between user/driver apps
- Maintained socket presence logic, channel subscriptions, and events

---

## ✅ Results

- The ride cycle is now stable, scalable, and auto-recovers from failures
- Queue jobs are optimized and cleared on success
- The dashboard reflects **accurate ride/driver stats**
- Feature delivery continued **without any downtime for real users**

---

## 🏗 Tech Stack

| Area | Tech |
|------|------|
| Backend | Laravel (PHP 8.x), MySQL |
| Queue | Redis, Laravel Horizon |
| Real-time | Pusher |
| Auth | Laravel Sanctum |
| Debugging | Laravel logs, Horizon |
| Mobile Apps | iOS (Swift), Android (Kotlin) |

---

## 📦 Repo Purpose

This repo is a **summary and work showcase only**.  
No source code is included due to ownership by the company.  
I built and maintained this system as part of my job at **Dinamo Egypt**.

---

## 👋 Let’s Talk

If you'd like to know more about my role in this system or how I tackled specific features like the ride assignment cycle or real-time queues — feel free to reach out!

I'm happy to break things down in interviews or DMs.
