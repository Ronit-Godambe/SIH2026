Live Preview - https://ronit-godambe.github.io/SIH2026/



# 🚆 Dynamic ETA Forecasting — Goa Express

### Smart India Hackathon 2026 · Problem Statement 26028

A web-based prototype demonstrating **dynamic Expected Time of Arrival (ETA) forecasting for coaching trains**.

The project demonstrates how future train arrival times can be continuously updated using the train's current state, historical running patterns, congestion, signal conditions, and other operational factors.

---

## 📌 Problem Statement

### Dynamic Forecast of Expected Time of Arrival (ETA) for Coaching Trains

Train delays are not static.

A train that is currently 10 minutes late may experience additional delays because of:

- Downstream congestion
- Signal restrictions
- Weather conditions
- Sectional running-time variations
- Historical delay patterns
- Network conditions

Therefore, simply adding the current delay to the scheduled timetable may not provide an accurate estimate of future arrival times.

The objective is to develop a system capable of **continuously forecasting and updating the ETA of trains at future stations**.

---

## 🚉 Existing Railway Information Systems

Indian Railways already has systems that provide train-position and operational information.

Examples include:

- **RTIS** — Real-time Train Information System
- **COA** — Control Office Application
- **NTES** — National Train Enquiry System

These systems provide important information about the current state and movement of trains.

Our project focuses on the **predictive layer**:

> Instead of only asking where the train is now, can we continuously estimate where it will reach next?

---

## 🧠 Proposed Solution

The proposed system acts as a **Dynamic ETA Prediction Layer** over existing railway information systems.

It considers multiple factors:

```text
Train Location
      +
Current Delay
      +
Historical Running Time
      +
Signal Conditions
      +
Downstream Congestion
      +
Weather
      ↓
ETA Prediction Engine
      ↓
Updated Future ETA
