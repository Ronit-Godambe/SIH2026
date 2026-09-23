Live Preview - https://ronit-godambe.github.io/SIH2026/

# 🚆 Dynamic ETA Forecasting — Goa Express

### Smart India Hackathon 2026 · Problem Statement 26028

A web-based prototype demonstrating **dynamic ETA forecasting for coaching trains** using real-time train conditions, historical running patterns, signal conditions, congestion, and weather factors.

---

## 📌 Problem Statement

Indian Railways operates thousands of trains across a large and complex railway network.

Traditional ETA estimation primarily depends on:

- Scheduled timetable
- Current train location
- Accumulated delay
- Average running time

However, actual train movement is affected by constantly changing conditions such as:

- Downstream congestion
- Signal restrictions
- Weather conditions
- Historical delay patterns
- Sectional running variations
- Network conditions

The objective is to develop a system that can **continuously forecast the expected arrival time of a train at future stations** by considering these changing conditions.

---

## 🚉 Existing Railway Information Systems

Indian Railways already has systems that provide operational and train-related information.

Examples include:

- **RTIS** — Real-Time Train Information System
- **COA** — Control Office Application
- **NTES** — National Train Enquiry System

These systems can provide information such as train location, movement and operational status.

However, the proposed system focuses specifically on an additional layer:

> **Predicting what is likely to happen next.**

Instead of only reporting the current delay, the system attempts to estimate how that delay may evolve along the remaining journey.

---

## 💡 Proposed Solution

The proposed system combines multiple data sources to continuously calculate a dynamic ETA.

### Input Parameters

The prediction engine considers:

- 📍 Current train location
- 🚆 Current train speed
- ⏱️ Current accumulated delay
- 🚦 Signal aspects and restrictions
- 🚧 Downstream congestion
- 🌧️ Weather conditions
- 📊 Historical sectional running times
- 🕐 Scheduled timetable
- 🛤️ Railway network conditions

The system continuously updates the prediction whenever new information becomes available.

---

## 🧠 Dynamic ETA Concept

Instead of simply calculating:

```text
Scheduled Remaining Time
+
Current Accumulated Delay
```

the proposed system estimates the additional time that may be introduced by future conditions.

Conceptually:

```text
Predicted Remaining Travel Time
+
Current Time
=
Dynamic ETA
```

The prediction can therefore change while the train is moving.

For example:

```text
Current Delay:       +8 min
Downstream Congestion: +5 min
Signal Restriction:    +2 min
Historical Pattern:    +3 min

Predicted Future Delay: +10 min

Dynamic ETA
= Current Time + Predicted Remaining Travel Time
```

---

# 🚆 Demonstration — Goa Express

The prototype demonstrates the concept using a simulated journey of the **Goa Express** from Goa to Delhi.

Example route:

```text
Vasco da Gama
      ↓
Madgaon Jn
      ↓
Belagavi
      ↓
Miraj Jn
      ↓
Pune Jn
      ↓
Bhopal Jn
      ↓
Jhansi Jn
      ↓
Gwalior Jn
      ↓
Agra Cantt
      ↓
Mathura Jn
      ↓
Hazrat Nizamuddin
```

The train moves through the simulated route while the ETA engine continuously updates its prediction.

---

# 📡 Live Demonstration

The prototype compares two approaches.

## 1. Conventional ETA Baseline

The conventional baseline estimates arrival using:

```text
Scheduled Remaining Time
+
Current Delay
```

This represents a simplified timetable-based approach.

---

## 2. Dynamic ETA Engine

The proposed engine additionally considers:

```text
Current Delay
+
Congestion
+
Signal Conditions
+
Historical Running Pattern
+
Weather
+
Network Conditions
```

The prediction is updated whenever the simulated railway conditions change.

---

## 🔄 Example

Suppose the train is currently:

```text
Running Delay: +8 minutes
```

A downstream congestion event is detected.

The dynamic engine may calculate:

```text
Congestion Impact: +5 min
Signal Impact:     +2 min
Historical Impact: +3 min
```

The system then updates the expected arrival time.

If the congestion later clears, the prediction can be reduced again.

This demonstrates the difference between:

```text
Static / Delay-Based ETA
```

and

```text
Dynamic / Predictive ETA
```

---

# ✨ Key Features

- 🚆 Real-time ETA simulation
- 📍 Train position tracking
- 🛤️ Station-by-station journey visualization
- 🚦 Signal restriction simulation
- 🚧 Downstream congestion simulation
- 🌧️ Weather impact simulation
- 📊 Historical delay influence
- 🔄 Continuous ETA updates
- 📈 Delay progression visualization
- ⚡ Conventional vs Dynamic ETA comparison
- 🔌 API-ready architecture
- 📱 Suitable for passenger-facing applications
- 🖥️ Suitable for railway control-room dashboards

---

# 🏗️ System Architecture

```text
                  ┌──────────────────────┐
                  │   Data Sources       │
                  │                      │
                  │ GPS / Location       │
                  │ Signals              │
                  │ Weather              │
                  │ Timetable            │
                  │ Historical Data      │
                  │ Network Conditions  │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Data Processing      │
                  │ & Validation         │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Feature Engineering  │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ ETA Prediction       │
                  │ Engine               │
                  │                      │
                  │ ML / Statistical    │
                  │ Models               │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Dynamic ETA          │
                  │ + Confidence Range   │
                  └──────────┬───────────┘
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
        Passenger App   Station Display   Control Room
```

---

# 🧩 Prototype Architecture

The current prototype simulates the data normally required by the prediction engine.

```text
Simulated Train Data
        │
        ▼
Train State Generator
        │
        ▼
Event Detection
        │
        ├── Congestion
        ├── Signal
        ├── Weather
        └── Historical Pattern
        │
        ▼
ETA Calculation
        │
        ▼
Live Dashboard
```

The architecture can later be connected to actual railway data feeds through APIs or other authorized data interfaces.

---

# 💻 Technology Stack

### Frontend

- HTML5
- CSS3
- JavaScript

### Data & Simulation

- JavaScript-based real-time simulation
- Simulated railway events
- Historical running-time dataset

### Future Backend

Possible technologies include:

- Python
- FastAPI
- Node.js
- REST APIs
- WebSockets

### Machine Learning

Potential models include:

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost-style models
- Time-series/statistical models

---

# 🤖 Machine Learning Approach

The system can initially use a simple baseline model.

### Baseline

```text
ETA =
Scheduled Remaining Time
+
Current Delay
```

The ML model can then learn the relationship between railway conditions and actual remaining travel time.

Example features:

```text
Current Speed
Current Delay
Distance Remaining
Historical Section Time
Day of Week
Time of Day
Weather
Signal Condition
Congestion Level
Previous Section Delay
```

The model predicts:

```text
Predicted Remaining Travel Time
```

Then:

```text
ETA = Current Time + Predicted Remaining Travel Time
```

---

# 📊 Evaluation

The system can be evaluated by comparing predicted arrival times against actual arrival times.

Possible metrics include:

### Mean Absolute Error (MAE)

```text
MAE =
Average |Predicted ETA - Actual ETA|
```

### Root Mean Square Error (RMSE)

```text
RMSE =
√(Average Prediction Error²)
```

The dynamic model can be compared against the baseline ETA method.

---

# 📈 Scalability

The proposed architecture is designed to support multiple trains simultaneously.

Conceptually:

```text
Train 1 ──┐
Train 2 ──┤
Train 3 ──┤
Train 4 ──┤──► ETA Prediction Engine
Train 5 ──┤
Train N ──┘
```

A production implementation could use:

- Event-driven processing
- Message queues
- Caching
- Asynchronous processing
- Distributed services
- Horizontal scaling

This would allow the system to process large numbers of train streams across different railway zones.

---

# 🚀 Future Implementation

The prototype can be extended with:

- Real railway data feeds
- GPS-based train tracking
- Live signal information
- Weather APIs
- Historical railway datasets
- Railway network graphs
- Advanced ML models
- Confidence intervals for ETA
- Mobile application integration
- Station display integration
- Control-room dashboards
- Large-scale distributed processing

---

# 💡 Core Innovation

The key idea is to move from:

```text
"What is the train's current delay?"
```

towards:

```text
"Given the train's current state and the conditions
ahead, when is it actually expected to arrive?"
```

The system continuously updates this prediction as the railway environment changes.

---

# ⚠️ Prototype Disclaimer

This project is a **prototype demonstration for Smart India Hackathon 2026**.

The train movement, GPS information, congestion, signal conditions, weather effects and historical patterns shown in the demonstration are **simulated data**.

The prototype does not claim to access or reproduce live internal Indian Railways systems.

The architecture is designed to demonstrate how such data could be processed by a future production system using authorized railway data sources.

---

# 👨‍💻 Author

**Ronit Godambe**

Computer Engineering Student  
Smart India Hackathon 2026

---

# 🏆 Smart India Hackathon 2026

**Problem Statement:** 26028  
**Title:** Dynamic Forecast of Expected Time of Arrival (ETA) for Coaching Trains  
**Organization:** Ministry of Railways  
**Category:** Software  
**Theme:** Smart Automation

---

⭐ Built as a prototype to demonstrate the concept of **dynamic railway ETA forecasting**.
