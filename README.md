````markdown
<div align="center">

<img src="PATH_TO_SIH_LOGO" height="90">

# IntelliFarm

### Edge-AI Smart Farming Assistant for Field-Level Crop Monitoring

**Team AgroInsight | Smart India Hackathon 2026 | PS ID: SIH 26180**

<img src="PATH_TO_IITB_LOGO" height="70">

</div>

---

## Project Demonstrations

<table>
<tr>
<td align="center" width="50%">

### 3D Probe Render

<video src="PATH_TO_PROBE_VIDEO" controls width="100%"></video>

</td>

<td align="center" width="50%">

### Working Prototype

<video src="PATH_TO_DEMO_VIDEO" controls width="100%"></video>

</td>
</tr>
</table>

---

## Project Explanation

<div align="center">

[![IntelliFarm Project Explanation](https://img.youtube.com/vi/UbcCrgo2Hvs/maxresdefault.jpg)](https://youtu.be/UbcCrgo2Hvs)

**Complete IntelliFarm Project Explanation**

</div>

---

## About IntelliFarm

IntelliFarm is a **field-deployable, low-power Edge-AI smart farming system** designed for small and marginal farmers, particularly in connectivity-constrained environments.

It combines **computer vision, multimodal sensing, open-set recognition, and distributed field probes** to provide localized crop-health intelligence.

The current prototype performs **fine-grained pest recognition and retrieval** using **DINOv2 (ViT-B/14)**, L2-normalized visual embeddings, and **Spherical K-Means prototype memory**.

---

## Current Prototype

- **25+ pest classes across 10 crops**
- Fine-grained pest recognition and retrieval
- Few-shot recognition
- Confidence estimation
- Unknown / novel pest detection
- Prototype-based retrieval using Spherical K-Means
- New pest classes without full model retraining
- On-device inference on Raspberry Pi 4B

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

## Technology

**Edge AI | Computer Vision | DINOv2 | Open-Set Recognition | Prototype Retrieval | IoT | Embedded Systems**

---

## Smart India Hackathon 2026

|                       |                                           |
| --------------------- | ----------------------------------------- |
| **Problem Statement** | SIH 26180                                 |
| **Theme**             | Agriculture, FoodTech & Rural Development |
| **Category**          | Hardware                                  |
| **Team**              | AgroInsight                               |
| **Team ID**           | 129026                                    |

---

<div align="center">

### Team AgroInsight

*Building practical Edge-AI systems for resilient, field-level agricultural intelligence.*

</div>
```
