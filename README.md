# IntelliFarm

### Edge-AI Smart Farming Assistant for Field-Level Crop Monitoring

**Team AgroInsight | Smart India Hackathon 2026 | PS ID: SIH 26180**

IntelliFarm is a **field-deployable, low-power Edge-AI smart farming system** designed for small and marginal farmers, particularly in connectivity-constrained environments.

It combines **computer vision, multimodal sensing, open-set recognition, and distributed field probes** to provide localized crop-health intelligence.

---

## Key Features

- **Edge AI:** Local AI inference on field probes, reducing dependence on continuous cloud connectivity
- **Computer Vision:** DINOv2-based fine-grained pest recognition and retrieval
- **Open-Set Recognition:** Detects potentially unknown or novel pests instead of forcing every observation into a known class
- **Multimodal Sensing:** Crop imagery combined with soil and environmental measurements
- **Low-Power Operation:** Periodic sensing, processing, communication, and sleep cycles
- **Distributed Monitoring:** Multiple probes for localized field monitoring and fault tolerance

### Current Prototype

- 25+ pest classes across 10 crops
- Few-shot recognition and retrieval
- Confidence estimation
- Unknown / novel pest detection
- Spherical K-Means prototype memory
- New pest classes without full model retraining
- Working Edge-AI prototype on Raspberry Pi 4B

**In development:** disease recognition, unknown disease detection, ROI and background processing, multimodal analysis, sensor redundancy, and distributed probe communication.

> Raspberry Pi 4B is used for the current prototype based on platform availability. The architecture is designed to be portable to **Qualcomm edge-AI hardware** for future deployment and optimization.

---

## System Overview

```text
Camera + Soil + Environment Sensors
                  |
                  v
           Raspberry Pi 4B
                  |
           Edge-AI Processing
                  |
      Pest Recognition / Retrieval
                  |
       Confidence + Assessment
                  |
       Structured Field Insights
                  |
          Wireless Communication
````

---

## Hardware

| Component          | Function                   |
| ------------------ | -------------------------- |
| Raspberry Pi 4B    | Edge AI and system control |
| IMX708 Camera      | Crop imaging               |
| Capacitive Sensors | Multi-depth soil moisture  |
| DHT22              | Temperature and humidity   |
| DS18B20            | Soil temperature           |
| TEMT6000           | Ambient light              |
| Battery + BMS      | Autonomous operation       |

---

# Project Demonstrations

## Project Explanation

[![IntelliFarm Project Explanation](https://img.youtube.com/vi/UbcCrgo2Hvs/maxresdefault.jpg)](https://youtu.be/UbcCrgo2Hvs)

## 3D Probe Render

<video src="videos/intellifarm-probe-render.MOV" controls width="800"></video>

## Working Prototype Demo

<video src="videos/intellifarm-prototype-demo.mp4" controls width="800"></video>

---

## Technology

**Edge AI | Computer Vision | DINOv2 | Open-Set Recognition | Prototype Retrieval | IoT | Embedded Systems**

---

## Smart India Hackathon 2026

**Problem Statement:** SIH 26180
**Theme:** Agriculture, FoodTech & Rural Development
**Category:** Hardware
**Team:** AgroInsight
**Team ID:** 129026

---

### Team AgroInsight

Developing practical Edge-AI and sensing systems for resilient, field-level agricultural intelligence.

```
```
