````markdown
# IntelliFarm

### Edge-AI Smart Farming Assistant for Field-Level Crop Monitoring

**Team AgroInsight | Smart India Hackathon 2026 | Problem Statement: SIH 26180**

IntelliFarm is a **field-deployable, low-power Edge-AI smart farming system** designed for small and marginal farmers, particularly in connectivity-constrained environments.

The system combines **computer vision, multimodal sensing, open-set recognition, and distributed field probes** to provide localized crop-health intelligence.

---

## Overview

Conventional crop monitoring often depends on manual inspection or cloud-connected systems. These approaches can become difficult to scale across heterogeneous fields and unreliable when connectivity is limited.

IntelliFarm addresses this by distributing intelligent sensing probes across the field.

Each probe combines:

- High-resolution crop imaging
- Multi-depth soil-moisture sensing
- Air temperature and humidity sensing
- Soil temperature sensing
- Ambient-light sensing
- Local Edge-AI inference
- Low-power autonomous operation
- Selective wireless communication

Instead of continuously transmitting raw sensor data and images to a remote server, the probe performs analysis locally and communicates **structured insights and relevant observations** when connectivity is available.

---

## System Architecture

```text
                    FIELD ENVIRONMENT
                           |
            +--------------+--------------+
            |              |              |
        Crop Images    Soil Signals   Environment
            |              |              |
            +--------------+--------------+
                           |
                    IntelliFarm Probe
                           |
        +------------------+------------------+
        |                                     |
   Camera Pipeline                       Sensor Pipeline
        |                                     |
   Image Processing                    Sensor Processing
        |                                     |
        +------------------+------------------+
                           |
                    Raspberry Pi 4B
                           |
                  Local Edge AI Layer
                           |
        +------------------+------------------+
        |                  |                  |
   Pest Recognition   Confidence / OOD   Sensor Context
        |                  |                  |
        +------------------+------------------+
                           |
                  Field-Level Assessment
                           |
                Structured Local Insights
                           |
                 Wireless Communication
````

The architecture is intentionally **hardware-independent at the AI and system-design level**. Raspberry Pi 4B is used in the current prototype because it was the edge-computing platform available to the team. The architecture can be adapted to **Qualcomm edge-AI hardware** for future deployment and optimization.

---

## Computer Vision and Edge AI

### Current Pest Recognition Pipeline

The current applied computer-vision implementation focuses on **fine-grained pest recognition and retrieval**.

The pipeline uses **DINOv2 ViT-B/14** with:

* Fine-tuned visual representations
* L2-normalized embeddings
* Spherical K-Means prototype memory
* Similarity-based retrieval
* Confidence estimation
* Few-shot recognition
* Open-set detection

The current prototype supports **25+ pest classes across 10 crops**.

New pest classes can be incorporated through the prototype-memory approach without requiring complete retraining of the visual backbone.

### Prototype-Based Retrieval

```text
Input Crop Image
      |
DINOv2 Feature Extraction
      |
L2-Normalized Embedding
      |
Prototype Memory
      |
Spherical K-Means
      |
Similarity Retrieval
      |
Top-K Candidate Analysis
      |
Confidence Estimation
      |
Known / Potentially Novel Pest
```

---

## Open-Set Recognition

Agricultural environments are inherently open-ended. A field may contain pests or disease conditions that were not present in the training data.

A conventional closed-set classifier may incorrectly assign an unfamiliar observation to one of its known classes.

IntelliFarm incorporates **open-set recognition** into its visual pipeline.

For pests, the current system supports:

* Known-class recognition
* Similarity-based retrieval
* Confidence estimation
* Unknown or novel pest detection

This approach will be extended to future disease recognition so that unfamiliar disease conditions can be flagged rather than being forced into an incorrect known category.

---

## Multimodal Field Sensing

Each IntelliFarm probe integrates visual and environmental measurements.

| Component                        | Measurement / Function             |
| -------------------------------- | ---------------------------------- |
| IMX708 Camera                    | High-resolution crop imaging       |
| Capacitive Soil Moisture Sensors | Soil moisture at multiple depths   |
| DHT22                            | Air temperature and humidity       |
| DS18B20                          | Soil temperature                   |
| TEMT6000                         | Ambient light                      |
| Raspberry Pi 4B                  | Edge processing and system control |
| Rechargeable Battery + BMS       | Autonomous power                   |
| Weather-resistant Enclosure      | Field deployment protection        |

### Sensor Reliability

**Sensor redundancy is planned for critical measurements** to improve reliability under sensor noise, drift, or individual sensor failure.

---

## Autonomous Operation

Each probe is designed for periodic autonomous operation.

```text
Capture
  |
Process
  |
Analyze
  |
Transmit
  |
Sleep
  |
Repeat
```

The low-power operating cycle reduces unnecessary computation and wireless communication while enabling extended autonomous operation.

---

## Connectivity

IntelliFarm is designed for environments where connectivity may be limited or intermittent.

When communication is available, probes can transmit structured information such as:

* Detected conditions
* Model predictions
* Confidence scores
* Sensor measurements
* Probe ID
* Timestamp
* Battery status

Images can be transmitted selectively when required rather than continuously streaming raw visual data.

Both **direct and multi-hop wireless communication** between probes are being evaluated for the distributed deployment architecture.

---

## Current Development Status

### Implemented

* Raspberry Pi 4B edge-computing prototype
* Integrated camera and environmental sensing
* Fine-grained pest recognition and retrieval
* DINOv2 ViT-B/14 visual representation
* L2-normalized embeddings
* Spherical K-Means prototype memory
* Similarity-based retrieval
* Top-K retrieval analysis
* Confidence estimation
* Few-shot pest recognition
* Open-set / unknown pest detection
* 25+ pests across 10 crops
* Addition of new pest classes through prototype memory
* Periodic probe operation
* Structured system outputs
* Working pest retrieval demonstration

### In Development

* Region-of-Interest extraction
* Background handling
* Robust image pre-processing
* Post-processing
* Improved field-image handling
* Disease recognition pipeline
* Integration of visual and sensor context
* Communication architecture
* Direct / multi-hop probe networking

### Planned

* Disease classification
* Unknown disease detection
* Nutrient-deficiency detection
* Plant growth-stage estimation
* Sensor redundancy for critical measurements
* Qualcomm edge-AI hardware transition
* Larger-scale field validation
* Extended autonomous deployment

---

## Project Demonstrations

### 3D Probe Render

[View 3D Probe Render](videos/intellifarm-probe-render.MOV)

### Working Prototype Demo

[View IntelliFarm Prototype Demo](videos/intellifarm-prototype-demo.mp4)

### Project Explanation

[![IntelliFarm Project Explanation](https://img.youtube.com/vi/UbcCrgo2Hvs/maxresdefault.jpg)](https://youtu.be/UbcCrgo2Hvs)

**Watch the complete IntelliFarm project explanation on YouTube.**

---

## Project Presentation

[View IntelliFarm SIH 2026 Presentation](IntelliFarm_SIH2026_Presentation.pdf)

---

## Technology Stack

**Edge AI | Computer Vision | DINOv2 | Open-Set Recognition | Prototype Retrieval | IoT | Embedded Systems**

---

## Expected Impact

IntelliFarm aims to provide farmers with localized and timely information that can support:

* Earlier pest intervention
* Earlier disease intervention
* Smarter irrigation
* Reduced unnecessary pesticide use
* Reduced unnecessary fertilizer use
* Lower agricultural input losses
* More efficient field monitoring
* Improved resilience under poor connectivity

---

## Smart India Hackathon 2026

| Field             | Details                                   |
| ----------------- | ----------------------------------------- |
| Problem Statement | SIH 26180                                 |
| Theme             | Agriculture, FoodTech & Rural Development |
| Category          | Hardware                                  |
| Team              | AgroInsight                               |
| Team ID           | 129026                                    |

---

## Team AgroInsight

AgroInsight is developing IntelliFarm as a field-oriented Edge-AI platform for intelligent and resilient agricultural monitoring.

The project combines **embedded systems, computer vision, machine learning, sensing, and distributed systems** to bring field-level intelligence closer to the crop.

---

## References

1. Wu et al., **IP102: A Large-Scale Benchmark Dataset for Insect Pest Recognition**, CVPR.
2. Oquab et al., **DINOv2: Learning Robust Visual Features without Supervision**, TMLR.
3. Research literature on Edge AI and IoT-enabled smart agriculture.
4. Agricultural intelligence and field-deployment systems including Plantix and related approaches.

```
```
