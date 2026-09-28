# 💧 Energy-Efficient Automatic Faucet for Water Conservation During Wudhu

An embedded systems project designed to reduce unnecessary water wastage during **wudhu (ablution)** using an automatic, touchless faucet. The system uses an **infrared proximity sensor**, **ATmega328P microcontroller**, and **latching solenoid valve** to control water flow only when required, while incorporating low-power techniques to improve energy efficiency.

---

## 📌 Project Overview

Water is often wasted when taps remain open during wudhu. A conventional faucet requires users to manually turn the water on and off, which can lead to unnecessary water consumption.

This project proposes an **energy-efficient, touchless automatic faucet** that detects the presence of a user's hand and controls water flow automatically.

By combining:

* Infrared proximity sensing
* Microcontroller-based control
* Solenoid valve operation
* Low-power embedded programming

the system aims to make water use more convenient, efficient, and sustainable.

---

## 🎯 Objectives

* Reduce unnecessary water consumption during wudhu.
* Automate water flow using a touchless sensing mechanism.
* Control a solenoid valve through a microcontroller.
* Reduce energy consumption using sleep modes and sensor duty cycling.
* Develop a practical and low-cost water conservation solution.
* Provide a solution suitable for mosques and other shared washing facilities.

---

## ✨ Key Features

* 🖐️ **Touchless Operation** — Detects hand presence using an infrared proximity sensor.
* 💧 **Automatic Water Control** — Automatically controls the water valve based on sensor input.
* ♻️ **Water Conservation** — Helps prevent unnecessary water flow.
* 🔋 **Low-Power Operation** — Supports microcontroller sleep modes and sensor duty cycling.
* ⚙️ **Embedded Control** — Built around the ATmega328P microcontroller.
* 🕌 **Mosque-Friendly Design** — Designed with wudhu areas and shared facilities in mind.
* 💰 **Low-Cost Prototype** — Uses commonly available embedded-system components.

---

# ⚙️ How It Works

The basic operating process is:

```text
        User's Hand
             │
             ▼
   TCRT5000 IR Sensor
             │
             ▼
       ATmega328P
      Microcontroller
             │
             ▼
     Valve Driver Circuit
             │
             ▼
    Latching Solenoid Valve
             │
             ▼
        Water Flow
```

### Operating Sequence

1. The **TCRT5000 infrared sensor** monitors the area near the faucet.
2. When a hand enters the detection area, the sensor generates a signal.
3. The **ATmega328P** reads and processes the sensor signal.
4. The microcontroller activates the **valve driver circuit**.
5. The driver provides the required control signal to the **latching solenoid valve**.
6. The valve opens and water begins to flow.
7. When the hand leaves the detection area, the controller determines that water is no longer required.
8. The valve is deactivated according to the programmed control logic.
9. The system can enter a low-power state when full processing is not required.

> **Note:** Exact sensor response, valve timing, and power-saving behaviour depend on the implemented firmware and hardware configuration.

---

# 🧩 System Architecture

```text
                   ┌─────────────────┐
                   │    User Hand    │
                   └────────┬────────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │ TCRT5000 IR     │
                   │ Proximity Sensor │
                   └────────┬────────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │   ATmega328P    │
                   │  Microcontroller│
                   └────────┬────────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │  Valve Driver   │
                   │     Circuit     │
                   └────────┬────────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │ Latching        │
                   │ Solenoid Valve  │
                   └────────┬────────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │   Water Flow    │
                   └─────────────────┘
```

---

# 🔩 Hardware Components

| Component                   | Purpose                                       |
| --------------------------- | --------------------------------------------- |
| **ATmega328P**              | Main embedded controller                      |
| **TCRT5000 IR Sensor**      | Detects nearby hand presence                  |
| **Latching Solenoid Valve** | Controls water flow                           |
| **Valve Driver Circuit**    | Interfaces the microcontroller with the valve |
| **Power Supply**            | Provides required operating power             |
| **Faucet & Water Line**     | Delivers water to the user                    |

### ⚠️ Hardware Safety

The valve driver and power supply must be selected according to the **voltage and current requirements of the solenoid valve**.

A suitable driver circuit and appropriate protection components should be used. Electrical components should also be protected from water exposure during installation.

---

# 💻 Technologies Used

* Embedded Systems
* ATmega328P
* C/C++ Embedded Programming
* Infrared Proximity Sensing
* Solenoid Valve Control
* Low-Power Embedded Design
* Sensor-Based Automation
* Water Conservation

---

# 🔋 Energy-Efficient Design

The project incorporates several low-power techniques.

## 1. Microcontroller Sleep Modes

The ATmega328P can enter a low-power sleep state when full processing is not required.

The controller can wake up when a configured interrupt or other suitable wake-up condition occurs.

This reduces unnecessary processor activity.

---

## 2. Sensor Duty Cycling

Where supported by the hardware and firmware, the sensor can be operated periodically instead of continuously.

For example:

```text
Sensor ON
    │
    ▼
Check Hand
    │
    ▼
Sensor OFF
    │
    ▼
Low-Power State
    │
    ▼
Repeat
```

This can reduce the average power consumption of the sensing system.

---

## 3. Demand-Based Valve Operation

The solenoid valve is activated only when the control logic determines that water is required.

This avoids unnecessary valve activation.

---

# 💧 Water Conservation

The primary purpose of the project is to reduce unnecessary water flow during wudhu.

The system automatically stops water flow when the user's hand is no longer detected according to the programmed control logic.

The actual amount of water saved depends on:

* User behaviour
* Water pressure
* Faucet flow rate
* Sensor placement
* Sensor response time
* Valve response time
* Number of users
* Duration of each wudhu session

Therefore, actual water-saving performance should be determined through experimental measurements.

---

# 📊 Example Water-Saving Estimation

Suppose a mosque achieves an **illustrative saving of 1,000 litres per day**.

| Period   | Estimated Water Saved |
| -------- | --------------------: |
| 1 Day    |          1,000 litres |
| 30 Days  |         30,000 litres |
| 365 Days |        365,000 litres |

### Calculation

```text
Monthly Saving

1,000 × 30
= 30,000 litres
```

```text
Annual Saving

1,000 × 365
= 365,000 litres
```

For 10 facilities achieving the same illustrative saving:

```text
365,000 × 10
= 3,650,000 litres/year
```

> ⚠️ These are **illustrative calculations**, not measured project results. Actual savings must be validated through field measurements.

---

# 🧪 Water-Saving Evaluation

A practical experiment can compare conventional and automatic faucet usage.

### Step 1 — Baseline Measurement

Measure the amount of water used by a conventional faucet during a defined number of wudhu sessions.

### Step 2 — Automatic Faucet Measurement

Repeat the test using the automatic faucet under comparable conditions.

### Step 3 — Record User Count

Record:

* Number of users
* Number of sessions
* Duration of testing
* Water consumption

### Step 4 — Calculate Average Consumption

```text
Average Water Consumption

Total Water Used / Number of Sessions
```

### Step 5 — Calculate Water Saved

```text
Water Saved

Baseline Water Use
-
Automatic Faucet Water Use
```

### Saving Percentage

```text
Saving Percentage

=
(Water Saved / Baseline Water Use) × 100
```

---

# 📏 Prototype Testing

The following parameters should be measured using the actual prototype.

| Parameter                   | Result         |
| --------------------------- | -------------- |
| Sensor Detection Range      | To be measured |
| Valve Response Time         | To be measured |
| Water Consumption / Session | To be measured |
| Water Saved / Session       | To be measured |
| Average Power Consumption   | To be measured |
| Battery/Power Runtime       | To be measured |
| Long-Term Reliability       | To be tested   |

> Experimental values should only be added after actual measurements are performed.

---

# 🖼️ Prototype

The following image shows the physical prototype of the automatic faucet system.

<p align="center">
  <img src="./assets/prototype.jpg" alt="Energy-Efficient Automatic Faucet Prototype" width="750">
</p>

### Prototype Includes

* ATmega328P microcontroller
* TCRT5000 IR sensor
* Latching solenoid valve
* Valve driver circuit
* Power supply
* Faucet/water-line assembly

> The image should represent the actual implemented prototype.

---

# 🎥 Workable Prototype Demonstration

The demonstration video shows the working operation of the prototype.

### Demonstration Flow

```text
Hand Detected
      │
      ▼
IR Sensor Activated
      │
      ▼
ATmega328P Processes Signal
      │
      ▼
Valve Driver Activated
      │
      ▼
Solenoid Valve Opens
      │
      ▼
Water Flows
      │
      ▼
Hand Removed
      │
      ▼
Valve Deactivated
      │
      ▼
Water Stops
```

### ▶️ Working Video

<p align="center">
  <video src="./assets/workable-demo.mp4" controls width="750">
    Your browser does not support embedded videos.
    <a href="./assets/workable-demo.mp4">Watch the workable prototype demonstration</a>
  </video>
</p>

**Demo file:**

`assets/workable-demo.mp4`

> GitHub's Markdown video rendering may vary depending on where the README is viewed. The MP4 file can also be opened directly from the repository.

---

# 📁 Project Structure

```text
energy-efficient-automatic-faucet/
│
├── README.md
│
├── assets/
│   ├── prototype.jpg
│   └── workable-demo.mp4
│
├── src/
│   └── ...
│
├── circuit/
│   └── ...
│
└── docs/
    └── ...
```

---

# ⚠️ Limitations

* TCRT5000 detection performance can vary with distance and surface characteristics.
* Ambient lighting and installation conditions may affect infrared sensing.
* Sensor placement has a significant effect on detection reliability.
* Water-saving performance depends on user behaviour and faucet flow rate.
* Latching solenoid valves require an appropriate control pulse.
* The valve driver must be designed according to the valve's electrical requirements.
* Water and electronics require appropriate physical isolation.
* Long-term durability requires extended real-world testing.
* Actual water savings cannot be determined without field measurements.

---

# 🚀 Future Improvements

Several improvements can be added to the prototype.

### 💧 Water Monitoring

* Add a calibrated flow sensor.
* Measure real-time water consumption.
* Calculate water savings automatically.

### 📊 Data Logging

* Store daily water consumption.
* Track number of wudhu sessions.
* Generate water-saving reports.

### ⚡ Energy Optimization

* Improve sleep-mode implementation.
* Optimize sensor duty cycling.
* Measure real-world power consumption.

### 🧠 Smart Control

* Add adaptive detection timing.
* Improve false detection handling.
* Add configurable valve timing.

### 🌐 IoT Monitoring

A future version could connect multiple faucets to a central monitoring system.

```text
Faucet 1 ──┐
Faucet 2 ──┤
Faucet 3 ──┼──► Central Monitoring System
Faucet 4 ──┤
Faucet 5 ──┘
```

This could allow facility managers to monitor:

* Water consumption
* Estimated savings
* Number of sessions
* System status
* Maintenance requirements

---

# 🌍 Potential Applications

The concept can potentially be used in:

* 🕌 Mosque wudhu areas
* 🏫 Educational institutions
* 🏥 Hospitals and clinics
* 🏢 Offices
* 🏘️ Community centres
* 🚻 Public washing facilities
* 🚿 Other shared water-use facilities

---

# 📷 Project Evidence

The repository should contain evidence of the actual implementation.

Recommended evidence includes:

* Prototype photographs
* Circuit/schematic diagram
* Hardware setup
* Sensor detection demonstration
* Automatic valve operation
* Water consumption measurements
* Power consumption measurements
* Working demonstration video
* Experimental results

Only actual project photographs, measurements, diagrams, and videos should be presented as project evidence.

---

# 🔬 Experimental Validation

Future testing should evaluate the system under realistic conditions.

### Suggested Test Parameters

| Test             | Measurement                     |
| ---------------- | ------------------------------- |
| Sensor Test      | Detection distance              |
| Response Test    | Sensor-to-valve response time   |
| Flow Test        | Litres/minute                   |
| Water Test       | Litres/session                  |
| Energy Test      | Average power consumption       |
| Reliability Test | Number of successful operations |
| Long-Term Test   | Performance over extended use   |

The results can then be used to determine the actual effectiveness of the system.

---

# 🕌 Real-World Deployment Concept

A possible mosque deployment could look like:

```text
             MOSQUE WUDHU AREA

       ┌──────────┐
       │ Faucet 1 │──┐
       └──────────┘  │
                     │
       ┌──────────┐  │
       │ Faucet 2 │──┤
       └──────────┘  │
                     │
       ┌──────────┐  │
       │ Faucet 3 │──┤
       └──────────┘  │
                     │
       ┌──────────┐  │
       │ Faucet N │──┘
       └──────────┘
             │
             ▼
      Water Conservation
```

Each faucet can operate independently using its own sensing and valve-control mechanism.

---

# 🎓 Project Category

**Embedded Systems / Sustainable Technology / Water Conservation / Automation**

### Core Technologies

```text
ATmega328P
     +
TCRT5000 IR Sensor
     +
Solenoid Valve
     +
Embedded Control
     +
Low-Power Design
     =
Automatic Water Conservation System
```

---

# 📝 Conclusion

The **Energy-Efficient Automatic Faucet for Water Conservation During Wudhu** demonstrates how embedded systems can be applied to address everyday water wastage.

By combining **infrared proximity sensing**, **microcontroller-based control**, **automatic valve operation**, and **low-power techniques**, the system provides a practical approach to controlling water flow in shared washing facilities.

The prototype demonstrates the concept of automatically supplying water when required and stopping unnecessary flow when the user is no longer detected.

Further field testing is required to quantify:

* Actual water savings
* Energy consumption
* Sensor reliability
* Valve response
* Long-term durability
* Real-world operational performance

---

# 👨‍💻 Project Information

| Information         | Details                                                               |
| ------------------- | --------------------------------------------------------------------- |
| **Project**         | Energy-Efficient Automatic Faucet for Water Conservation During Wudhu |
| **Category**        | Embedded Systems / Sustainable Technology                             |
| **Microcontroller** | ATmega328P                                                            |
| **Sensor**          | TCRT5000 IR Proximity Sensor                                          |
| **Actuator**        | Latching Solenoid Valve                                               |
| **Control**         | Automatic / Touchless                                                 |
| **Application**     | Wudhu & Shared Washing Facilities                                     |

---

## 🌱 Vision

> **Making everyday water use smarter, more efficient, and more sustainable.**

---

g