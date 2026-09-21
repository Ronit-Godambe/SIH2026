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


Whenever railway conditions change, the predicted ETA can be recalculated.

🚆 Demonstration — Goa Express

The prototype uses Goa Express (12779) as a demonstration train.

The journey is represented as a compressed simulation from:

Vasco da Gama → Hazrat Nizamuddin

The demonstration includes stations such as:

Vasco da Gama
Madgaon Jn
Belagavi
Miraj Jn
Pune Jn
Bhopal Jn
Jhansi Jn
Gwalior Jn
Agra Cantt
Mathura Jn
Hazrat Nizamuddin

⚠️ The journey data used in the prototype is simulated for demonstration purposes and is not a live Indian Railways data feed.

⚡ Live Demonstration

The main part of the prototype compares two approaches.

Conventional ETA Baseline

The baseline uses:

Scheduled Remaining Time
+
Current Accumulated Delay

This represents a simple ETA calculation.

Dynamic ETA Engine

Our proposed system additionally considers:

Current Delay
+
Historical Section Behaviour
+
Signal Conditions
+
Downstream Congestion
+
Weather

The ETA is recalculated as conditions change.

Example

Suppose a train currently has:

Current Delay       +8 min
Congestion          +5 min
Signal Restriction  +2 min
Historical Pattern  +3 min

The dynamic prediction can account for these additional factors rather than assuming that the current delay will remain unchanged.

During the simulation, these conditions change and the ETA is updated accordingly.

🎯 Key Features
🚆 Train Simulation — A compressed Goa Express journey is simulated over approximately 2–3 minutes.
📍 Live Train Position — The current location of the train changes as the simulation progresses.
⏱️ Dynamic ETA — ETA values are continuously recalculated during the simulation.
🚦 Signal Effects — Signal restrictions can contribute additional predicted delay.
🚧 Congestion — Downstream congestion affects the predicted arrival time.
📊 Historical Patterns — Historical section behaviour contributes to the prediction.
🌧️ Weather Effects — Simulated weather conditions can influence the prediction.
🔄 Real-Time Updates — The prediction changes as new events occur.
📈 Baseline Comparison — Conventional and dynamic ETA calculations are displayed side-by-side.
⏹️ Simulation Controls — The demonstration can be started and stopped.
📱 Responsive Design — The interface is designed for desktop and mobile screens.
🏗️ System Architecture
                    DATA SOURCES
                         │
          ┌──────────────┼──────────────┐
          │              │              │
     Train Data      Historical     Network Data
          │              │              │
          └──────────────┼──────────────┘
                         ↓
                  Data Processing
                         ↓
                 Feature Engineering
                         ↓
                  ETA Prediction
                         ↓
                 Dynamic ETA Engine
                         ↓
              ┌──────────┼──────────┐
              ↓          ↓          ↓
          Passenger    Station    Control Room
            Apps       Displays    Dashboard
🧪 Prototype Architecture

The current prototype is intentionally lightweight.

Everything is contained inside a single:

index.html

It contains:

HTML
CSS
JavaScript

No backend is required to run the current demonstration.

The simulation generates the train's movement and changing operational conditions locally in the browser.

🛠️ Technology Stack
Technology	Purpose
HTML5	Page structure
CSS3	Interface and responsive design
JavaScript	Train simulation and ETA calculations
Browser	Prototype execution
🤖 Machine Learning Approach

A future implementation can begin with a simple baseline and progressively introduce machine-learning models.

Baseline
ETA = Current Time
      +
Scheduled Remaining Travel Time
      +
Current Delay
ML-Based Approach

Potential models include:

Linear Regression
Random Forest
Gradient Boosting
XGBoost-style models
Time-series / statistical forecasting models

The model can predict remaining travel time, after which:

ETA = Current Time + Predicted Remaining Travel Time

Model performance can be evaluated using:

MAE — Mean Absolute Error
RMSE — Root Mean Square Error

Actual performance values should be obtained from test data rather than assumed.

📈 Evaluation

The system can compare:

Scheduled ETA
      ↓
Baseline ETA
      ↓
Dynamic ETA
      ↓
Actual Arrival

This allows prediction error to be measured at each station.

Prediction
     ↓
Station Reached
     ↓
Actual Arrival Recorded
     ↓
Prediction Error Calculated
     ↓
Model Performance Evaluated
🌐 Scalability

The prototype demonstrates one simulated train.

A production architecture could support many trains simultaneously by processing each train as an independent real-time prediction stream.

The architecture can eventually be extended using:

APIs
Event-driven processing
Distributed services
Databases
Caching
Horizontal scaling
Model-serving infrastructure
🔮 Future Implementation

The current prototype uses simulated data.

A production-oriented implementation could replace the simulation layer with real operational feeds such as:

Real-Time Train Location
        ↓
Signal Information
        ↓
Timetable Data
        ↓
Historical Delay Database
        ↓
Weather Data
        ↓
Network / Congestion Data
        ↓
ML / Statistical Model
        ↓
Dynamic ETA API

The prediction engine could then continuously update ETAs for multiple trains across multiple railway zones.

💡 Core Innovation

The central idea of the project is:

Continuously update future train ETAs using both the current state of the train and changing conditions across the railway network.

Instead of treating delay as a fixed value:

Current Delay = Future Delay

the system treats delay as something that can evolve:

Current State
      ↓
Prediction
      ↓
New Event
      ↓
Updated Prediction
      ↓
Another Event
      ↓
Updated Prediction
⚠️ Prototype Disclaimer

This project is a demonstration prototype.

It does not claim to reproduce the proprietary internal systems or algorithms of Indian Railways.

The Goa Express journey, operational events, delays, and prediction values shown in the demo are simulated to demonstrate the concept of dynamic ETA forecasting.

🚀 Running the Prototype

No installation is required.

Simply open:

index.html

in a modern web browser.

Navigate to:

05 — Watch the Difference

Then click:

▶ START DEMO

The simulation can be stopped using:

■ STOP
👨‍💻 Author

Designed and Developed by Ronit Godambe

🇮🇳 Smart India Hackathon 2026

Problem Statement: 26028
Title: Dynamic Forecast of Expected Time of Arrival (ETA) for Coaching Trains
Organization: Ministry of Railways
Category: Software
Theme: Smart Automation
