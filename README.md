<div align="center">

# IntelliFarm

### Edge-AI for field-level crop intelligence

**AgroInsight · Smart India Hackathon 2026**

</div>

<br>

<div align="center">

[![Project Explanation](https://img.youtube.com/vi/UbcCrgo2Hvs/maxresdefault.jpg)](https://youtu.be/UbcCrgo2Hvs)

**Project Explanation**

</div>

---

## Field intelligence, without the cloud.

IntelliFarm is a **low-power Edge-AI farming system** that brings crop monitoring directly to the field.

Distributed probes combine **computer vision + soil and environmental sensing** to detect crop-health problems locally, even with intermittent connectivity.

### What we have built

**25+ pests · 10 crops · On-device AI · Open-set recognition**

Our current vision system uses **fine-tuned DINOv2 ViT-B/14** with a **Spherical K-Means prototype memory** for:

- Fine-grained pest recognition and retrieval
- Few-shot class addition
- Confidence estimation
- Unknown / novel pest detection

New pest classes can be added without full model retraining.

### The probe

**Raspberry Pi 4B · IMX708 Camera · Soil Moisture · DHT22 · DS18B20 · TEMT6000**

Each probe periodically **captures, analyzes, transmits, and sleeps**, reducing power and communication requirements.

Visual predictions are combined with sensor context to produce structured field-level insights. Selective image transmission and distributed probes reduce dependence on continuous connectivity and provide resilience to individual probe failures.

### Beyond pests

The same open-set framework is being extended toward **disease recognition and unknown disease detection**, with ROI extraction, background handling, and robust image preprocessing currently in development.

Nutrient-deficiency detection and growth-stage estimation are future extensions.

### Built for the edge

The current prototype runs on **Raspberry Pi 4B**, while the architecture is designed to transition to **Qualcomm edge-AI hardware** for deployment and optimization.

---

<div align="center">

**Edge AI · Computer Vision · DINOv2 · Open-Set Recognition · IoT**

### Team AgroInsight

</div>
