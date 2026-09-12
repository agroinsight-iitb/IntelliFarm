<div align="center">

# IntelliFarm

**Edge-AI Smart Farming Assistant for Field-Level Crop Monitoring**

**AgroInsight | Smart India Hackathon 2026**



---

## Overview

IntelliFarm is a **distributed Edge-AI system for field-level crop monitoring**. Each probe combines crop imaging with soil and environmental sensing and performs local inference, reducing dependence on continuous cloud connectivity.

The current prototype runs on a **Raspberry Pi 4B** and supports autonomous periodic sensing, local analysis, selective communication, and low-power operation.

## Pest Recognition

The current vision pipeline uses **fine-tuned DINOv2 ViT-B/14** to extract L2-normalised visual embeddings. Pest classes are represented using a **Spherical K-Means prototype memory**, enabling similarity-based retrieval and few-shot class extension.

Current capabilities include:

* Fine-grained pest recognition and retrieval
* Top-K prototype retrieval
* Confidence estimation
* Few-shot addition of new classes
* Open-set detection of unknown pests

**25+ pests across 10 crops** are currently supported.

## Field Sensing

Each probe combines vision with:

| Sensor             | Measurement                      |
| ------------------ | -------------------------------- |
| IMX708             | Crop imagery                     |
| Capacitive sensors | Soil moisture at multiple depths |
| DHT22              | Air temperature and humidity     |
| DS18B20            | Soil temperature                 |
| TEMT6000           | Ambient light                    |

The probe operates through periodic **capture, processing, transmission, and sleep** cycles. Structured outputs contain model predictions, confidence, sensor measurements, probe information, timestamps, and battery status.

## Architecture

The system is designed around **local intelligence and distributed sensing**. Raw images are not continuously transmitted; structured insights are prioritized and images can be sent selectively when required.

Direct and multi-hop probe communication is being evaluated. Distributed probes provide resilience to individual probe failures.

The current Raspberry Pi implementation is a prototype platform rather than an architectural dependency. The system can be adapted to **Qualcomm edge-AI hardware** for future deployment and optimization.

## Development

The pest recognition pipeline is implemented and being extended with **ROI extraction, background handling, and image pre/post-processing** for field conditions.

The same open-set approach is intended for **disease recognition and unknown disease detection**. Nutrient-deficiency analysis and growth-stage estimation are additional planned capabilities.

---

<div align="center">

**Edge AI · Computer Vision · DINOv2 · Open-Set Recognition · IoT**

**Team AgroInsight**

</div>
