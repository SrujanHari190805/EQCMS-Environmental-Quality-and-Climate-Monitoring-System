# 🌿 EQCMS – Environmental Quality & Climate Monitoring System

> **Innovator Award 2025 | Deployed at BMSIT&M Campus**

A single low-power embedded device that consolidates six environmental parameters — AQI, temperature, humidity, atmospheric pressure, and more — into a continuous cloud-synced monitoring system.

---

## 📌 Problem Statement

Monitoring environmental quality across a large institutional campus requires expensive, fragmented sensor installations with no unified data visibility. Manual inspection is time-consuming and fails to capture temporal trends crucial for informed decision-making.

---

## 💡 Solution

EQCMS is a compact, multi-sensor embedded unit that continuously measures six climate and air-quality parameters, syncs data to the cloud via ThingSpeak, and provides a real-time remote dashboard for institution-wide environmental awareness.

---

## 🏗️ System Architecture

```
[Sensors]
   ├── MQ135 – Air Quality Index (AQI)
   ├── DHT22 – Temperature & Humidity
   ├── BMP280 – Atmospheric Pressure
   └── Additional Climate Sensors
         │
   [Microcontroller – ESP32]
         │  Embedded C Firmware
         ├── Periodic data acquisition
         ├── Data preprocessing
         └── Wi-Fi cloud sync
         │
   [ThingSpeak Cloud]
         └── Real-time dashboard
         └── Historical logging
         └── Remote visualization
```

---

## ⚙️ Hardware Stack

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller with Wi-Fi |
| MQ135 | Air quality / AQI measurement |
| DHT22 | Temperature & humidity |
| BMP280 | Atmospheric pressure |
| OLED Display | Local real-time readout |
| LiPo Battery | Portable / low-power operation |

---

## 💻 Firmware Overview

- **Language:** Embedded C
- **Platform:** ESP32 (Arduino framework)
- **Key Features:**
  - Periodic sensor polling at configurable intervals
  - Data validation and outlier filtering
  - Wi-Fi-based cloud synchronisation to ThingSpeak
  - Local OLED display for on-site readings
  - Low-power sleep mode between acquisition cycles

---

## 📊 Monitored Parameters

| Parameter | Sensor | Unit |
|---|---|---|
| Air Quality Index | MQ135 | ppm |
| Temperature | DHT22 | °C |
| Relative Humidity | DHT22 | % |
| Atmospheric Pressure | BMP280 | hPa |
| Heat Index | Computed | °C |
| Dew Point | Computed | °C |

---

## ☁️ Cloud Dashboard

- **Platform:** ThingSpeak
- Live graphs for all 6 parameters
- Historical trend analysis
- Configurable alert thresholds
- Accessible remotely from any device

---

## 🚀 Deployment

- Deployed across **BMSIT&M campus** for institution-wide periodic data collection
- Continuous operation for real-world data capture
- Used for environmental trend reporting to campus administration

---

## 🏆 Recognition

- 🥇 **Innovator Award 2025** – BMSIT&M, awarded for demonstrated real-world impact

---

## 👤 Author

**Sri Srujan Hari T**
B.E – Electronics & Communication Engineering, BMSIT&M
[LinkedIn](https://www.linkedin.com/in/srujan-hari-undefined-1a7364399) | thammineedisrujanhari@gmail.com
