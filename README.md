<div align="center">

# IntelliFarm

### Edge-AI Smart Farming Assistant for Field-Level Crop Monitoring

**AgroInsight | Smart India Hackathon 2026**

</div>

<br>

<div align="center">

<table>
<tr>
<td align="center" width="50%">

### 3D Probe

<br>

<video src="videos/intellifarm-probe-render.MOV" controls width="100%"></video>

</td>

<td align="center" width="50%">

### Working Prototype

<br>

<video src="videos/intellifarm-prototype-demo.mp4" controls width="100%"></video>

</td>
</tr>
</table>

</div>

<br>

<div align="center">

[![Project Explanation](https://img.youtube.com/vi/UbcCrgo2Hvs/maxresdefault.jpg)](https://youtu.be/UbcCrgo2Hvs)

**Project Explanation**

</div>

---

## Overview

**IntelliFarm** is a field-deployable, low-power **Edge-AI smart farming system** designed for localized crop monitoring in connectivity-constrained environments. Distributed field probes combine computer vision with soil and environmental sensing to provide timely information about crop health and field conditions without requiring continuous cloud connectivity.

Each probe periodically captures crop imagery and measures **soil moisture at multiple depths, air temperature, humidity, soil temperature, and ambient light**. The current prototype uses a **Raspberry Pi 4B** for local processing, camera control, sensor acquisition, and communication.

The probe follows an autonomous periodic cycle:

**Capture → Process → Transmit → Sleep**

This reduces unnecessary communication and supports operation under limited power and intermittent connectivity.

## Edge-AI & Computer Vision

The current computer-vision implementation focuses on **fine-grained pest recognition and retrieval**. A fine-tuned **DINOv2 ViT-B/14** model generates L2-normalised visual embeddings. A **Spherical K-Means prototype memory** represents pest classes and enables similarity-based retrieval.

The system currently supports:

- Fine-grained pest recognition and retrieval
- Prototype-based few-shot recognition
- Confidence estimation
- Top-K similarity retrieval
- Open-set detection of unknown or novel pests
- Addition of new pest classes without full model retraining

The current prototype covers **25+ pests across 10 crops**.

Open-set recognition is particularly important for agricultural deployment because field observations may contain conditions that are not represented in a fixed training taxonomy. The implemented pest pipeline therefore distinguishes recognized classes from potentially novel observations instead of forcing every sample into a known category.

The vision pipeline is being extended with **Region-of-Interest extraction, background handling, and pre/post-processing** to improve robustness on field imagery. The same open-set approach is intended to extend to **disease classification and unknown disease detection**. Additional planned visual capabilities include nutrient-deficiency detection and plant growth-stage estimation.

## Multimodal Field Sensing

Visual predictions are complemented by environmental measurements, providing contextual information for field-level assessment.

**Sensors**

| Component | Purpose |
|---|---|
| IMX708 Camera | Crop and pest imaging |
| Capacitive Soil Moisture | Moisture measurement at multiple depths |
| DHT22 | Air temperature and humidity |
| DS18B20 | Soil temperature |
| TEMT6000 | Ambient light |

Sensor readings and model outputs are combined into structured field insights containing detected conditions, confidence, sensor context, probe information, timestamps, and battery status. **Sensor redundancy for critical measurements is planned** to improve reliability under noise or individual sensor failure.

## Distributed & Connectivity-Aware Design

Instead of continuously transmitting raw imagery, probes prioritize **structured insights and sensor measurements**, with images transmitted selectively when required. Direct and multi-hop wireless communication between probes is being evaluated.

The distributed architecture also provides **fault tolerance**: failure of an individual probe does not disable the complete monitoring system.

## Hardware & Portability

The current prototype integrates:

**Raspberry Pi 4B · IMX708 Camera · Soil Moisture Sensors · DHT22 · DS18B20 · TEMT6000 · Rechargeable Battery with BMS · Weather-Resistant Enclosure**

Raspberry Pi 4B was selected for the current prototype because it was the edge-computing platform available to the team. The software architecture is not tied to Raspberry Pi and can be adapted to **Qualcomm edge-AI hardware** for future deployment and optimization.

## Current Status

**Implemented:** Edge sensing, Raspberry Pi integration, pest retrieval, prototype memory, few-shot recognition, confidence estimation, and pest open-set detection.

**In Development:** Robust field-image preprocessing, ROI extraction, background handling, disease analysis, and distributed probe communication.

**Planned:** Disease open-set recognition, nutrient-deficiency analysis, growth-stage estimation, sensor redundancy, and further edge-hardware optimization.

---

<div align="center">

**Edge AI · Computer Vision · DINOv2 · Open-Set Recognition · IoT · Embedded Systems**

**Team AgroInsight**

</div>
