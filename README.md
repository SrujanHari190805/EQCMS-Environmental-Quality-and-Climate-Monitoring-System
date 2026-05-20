# EQCMS – Environmental Quality & Climate Monitoring System

> An industrial-grade, solar-powered IoT environmental monitoring node deployed on the BMSIT&M campus. Monitors PM1.0, PM2.5, PM10, CO, temperature, and humidity in real-time with a live Grafana dashboard.

![Deployed on campus since August 2025](https://img.shields.io/badge/Deployed-August%202025-green)
![Award](https://img.shields.io/badge/Award-Innovator%202025-gold)
![UN SDGs](https://img.shields.io/badge/UN%20SDGs-3%2C%2011%2C%2013-blue)

---

## 📌 What It Does

EQCMS is a permanent campus infrastructure asset that continuously measures six environmental parameters and transmits them to a live online dashboard. It calculates the **National Air Quality Index (NAQI)** and triggers alerts for hazardous levels. It has been running uninterrupted since August 2025, generating a validated longitudinal air quality dataset.

---

## 🖼️ Suggested Media to Add

| What to Add | Where to Get It |
|---|---|
| Photo of the deployed node on the campus electric pole | Take from your field deployment |
| Screenshot of the live Grafana dashboard | Export from your Grafana instance |
| Long-term PM trend graph (Nov 2025 – Jan 2026) | Export from the report/dashboard |
| Short-term air quality graph (Jan 25 – Feb 3, 2026) | Export from the report |
| Temperature flat-line graph (Nov 30, 2025 cyclone day) | Export from the report |
| Circuit/wiring diagram | From EQCMS report Fig 1 |
| Block diagram | From EQCMS report Fig 2 |
| Flow diagram | From EQCMS report Fig 3 |

---

## 🏗️ System Architecture

```
[Solar Panel 18V/20W] → [PWM Charge Controller] → [12V 14Ah Li-Ion Battery]
                                                           ↓
                                                    [Raspberry Pi 5]
                                                    /      |       \
                              [SN-GCJA5 PM Sensor] [PS1-CO-1000] [SEN0438 RS485]
                              via UART              via UART       via RS485
                                                           ↓
                                              [Edge Processing (NAQI calc)]
                                                           ↓
                                              [MQTT → Grafana Dashboard]
                                                           ↓
                                                  [LED Display (on-site)]
```

---

## 🔧 Hardware Components

| Component | Model | Purpose |
|---|---|---|
| Main Controller | Raspberry Pi 5 | Edge processing, MQTT, NAQI computation |
| PM Sensor | Panasonic SN-GCJA5 (Laser Scattering) | RSPM 1.0, RSPM 2.5, SPM 10 |
| CO Sensor | Amphenol PS1-CO-1000-MOD (Solid Polymer Electrolyte) | 0–1000 ppm CO detection |
| Temp/Humidity | DFRobot SEN0438 (RS485 Modbus RTU) | ±0.3°C, ±2% RH accuracy |
| Solar Panel | 18V, 20W | Primary power source |
| Battery | 12V, 14Ah Li-Ion | Energy storage for 24/7 operation |
| Charge Controller | 30A PWM | Solar charging management |
| Display | LED Screen | On-site real-time parameter display |
| Enclosure | IP-rated polycarbonate | Weatherproof outdoor housing |

### Why Industrial-Grade Sensors?

- **SN-GCJA5** uses **laser scattering** (not LED-based), distinguishing PM1.0, PM2.5, and PM10 precisely, with onboard auto-calibration for lens drift.
- **PS1-CO-1000-MOD** uses **Solid Polymer Electrolyte** technology for CO selectivity, >5 year lifespan, and stability against humidity — unlike typical metal-oxide sensors.
- **SEN0438** uses **RS485 differential signaling** for noise immunity in outdoor environments, with a SHT-series sensing element protected by a sintered metal filter.

---

## 📊 Key Results & Data Insights

### Live Dashboard Snapshot
- Temperature: **27.6°C**, Humidity: **65.4%**
- CO: **0.95 mg/m³** (well below the hazardous threshold of 2–4 mg/m³)
- NAQI: **23.6** — classified as **"Good"**

### Long-Term Trends (Nov 2025 – Jan 2026)
- Clear seasonal inversion observed in winter: SPM 10 frequently peaked above 60–70 µg/m³ in December/January vs. below 20 µg/m³ in early November.
- High daily volatility (sawtooth pattern) correlates with traffic activity near the parking zone.

### Significant Event: Cyclone Ditwah (Nov 30, 2025)
- Temperature held flat between 19–21°C for the entire day (10 AM – 5:30 PM) — a "day without a noon."
- Validated sensor integrity under heavy cloud cover, cold winds, and moisture exposure.

---

## ⚙️ Software Stack

- **Firmware**: Python on Raspberry Pi 5, reading UART (PM + CO) and RS485 (Temp/Humidity via Modbus RTU)
- **Protocol**: MQTT for telemetry transmission
- **Dashboard**: Grafana (live, web-accessible)
- **Alerts**: Threshold-based NAQI and heat-index alerts

---

## 📍 Deployment

- **Location**: First electric pole along the BMSIT&M campus double road
- **Placement rationale**: Adjacent to vehicular pathway and two-wheeler parking for direct capture of combustion emissions; optimal solar irradiance at mounting height
- **Online since**: August 2025

---

## 🏆 Recognition

- 🏅 **Innovator Award 2025** — BMSIT&M
- 🌍 Cited in alignment with **UN SDGs 3** (Good Health), **11** (Sustainable Cities), **13** (Climate Action)

---

## 👥 Team

| Name | Roll No. |
|---|---|
| K S Nitish | 1BY23EC052 |
| Sri Srujan Hari T | 1BY23EC106 |
| Tarun Patil | 1BY23EC113 |

**Guided by:** Dr. Rajesh Gopinath, Professor, Dept. of Civil Engineering & Key Liaison, Eco Club, BMSIT&M

---

## 🔮 Future Scope

- Expand to a distributed multi-node sensor network across the campus
- Integrate predictive environmental modelling using historical dataset
- Add pH and noise pollution sensors
- Develop a public-facing mobile app for campus community alerts
