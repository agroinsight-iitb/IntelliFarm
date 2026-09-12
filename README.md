# 🌱 IntelliFarm

### Edge-AI Smart Farming for Small and Marginal Farmers

**IntelliFarm** is a field-deployable, low-power smart farming system that combines **computer vision, soil and environmental sensing, and Edge AI** to provide localized intelligence directly at the field level.

The system uses distributed field probes to periodically capture crop images and measure soil and environmental conditions. AI inference is performed locally on the edge device, reducing dependence on continuous internet connectivity and cloud processing.

> **Built by Team AgroInsight | Smart India Hackathon 2026 | PS 26180**

---

## 🚜 What is IntelliFarm?

Agricultural fields are heterogeneous, connectivity can be unreliable, and crop-health problems are often detected only after significant damage has occurred.

IntelliFarm addresses this through a distributed sensing architecture in which individual probes monitor specific field zones.

Each probe combines:

* 📷 Crop imaging
* 💧 Multi-depth soil-moisture sensing
* 🌡️ Soil and air temperature sensing
* 💦 Humidity sensing
* ☀️ Ambient-light sensing
* 🧠 On-device AI inference
* 📡 Low-power communication
* 🔋 Autonomous battery-powered operation

Rather than continuously transmitting raw data to the cloud, the probe performs local processing and transmits relevant insights when connectivity is available.

---

## 🧠 Edge-AI Pipeline

```text
Sense → Analyze → Detect → Assess → Alert
```

The probe periodically captures observations, processes them locally, evaluates the detected condition and confidence, and generates structured information for transmission.

The current prototype performs AI inference directly on a **Raspberry Pi 4B**.

The Raspberry Pi was selected for the prototype because it was the edge-computing platform available to us. The architecture is not tied to Raspberry Pi and can be adapted to **Qualcomm edge-AI platforms** for future deployment and optimization.

---

## 🔬 Current Computer Vision System

Our current implementation focuses on **fine-grained pest recognition and retrieval**.

The retrieval system uses:

* **DINOv2 ViT-B/14** visual embeddings
* L2-normalised embeddings
* **Spherical K-Means** prototype memory
* Similarity-based prototype retrieval
* Confidence estimation
* Few-shot recognition
* Open-set recognition
* Unknown / novel pest detection

The current prototype supports:

**25+ pests across 10 crops**

New pest classes can be incorporated through prototype updates without requiring complete model retraining.

### Open-set Recognition

A central design principle of IntelliFarm is that field observations should not always be forced into a predefined set of known classes.

The current pest system can:

1. Retrieve known pest classes
2. Estimate prediction confidence
3. Detect potentially unknown or novel pests

This capability has been implemented and demonstrated for the pest-recognition use case.

The same approach will be extended to **disease classification and unknown disease detection**.

---

## 🖼️ Vision Pipeline Development

The vision pipeline is being extended to improve robustness on real field imagery.

Planned and ongoing components include:

* Region-of-Interest (ROI) extraction
* Background handling
* Image pre-processing
* Post-processing
* Confidence-based assessment
* Unknown-condition detection

Future visual-analysis capabilities include:

* 🐛 Pest recognition
* 🦠 Disease classification
* 🔎 Unknown disease detection
* 🧪 Nutrient-deficiency detection
* 🌱 Plant growth-stage estimation

---

## 🌾 Multimodal Field Sensing

Visual observations are combined with physical field measurements to provide additional context.

### Sensors

| Component                        | Purpose                            |
| -------------------------------- | ---------------------------------- |
| IMX708 Camera                    | Crop imaging                       |
| Capacitive Soil-Moisture Sensors | Soil moisture at multiple depths   |
| DHT22                            | Air temperature and humidity       |
| DS18B20                          | Soil temperature                   |
| TEMT6000                         | Ambient light                      |
| Raspberry Pi 4B                  | Edge processing and system control |
| Rechargeable Battery + BMS       | Autonomous power                   |
| Weather-resistant enclosure      | Field deployment                   |

Sensor measurements can be used alongside visual predictions for localized field assessment.

### Sensor Reliability

Sensor redundancy is planned for critical measurements to improve reliability in the presence of sensor noise or individual sensor failure.

---

## 📡 Connectivity and Edge Operation

IntelliFarm is designed for agricultural environments with poor or intermittent connectivity.

Each probe operates through a periodic low-power cycle:

```text
Capture → Process → Transmit → Sleep
```

When communication is available, the system can transmit:

* Structured insights
* Sensor measurements
* Model predictions
* Confidence information
* Probe ID
* Timestamp
* Battery status

Images can be transmitted selectively rather than continuously.

Direct and multi-hop wireless communication between probes is being evaluated.

The distributed architecture also provides fault tolerance: failure of one probe does not disable the complete monitoring system.

---

## 🏗️ System Architecture

```text
                    ┌─────────────────────────┐
                    │      Field Gateway      │
                    │                         │
                    │  Aggregation / Insights │
                    └────────────┬────────────┘
                                 │
                    Low-power wireless link
                                 │
             ┌───────────────────┼───────────────────┐
             │                   │                   │
             ▼                   ▼                   ▼
      ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
      │ Field Probe │     │ Field Probe │     │ Field Probe │
      │      01     │     │      02     │     │      03     │
      ├─────────────┤     ├─────────────┤     ├─────────────┤
      │ Camera      │     │ Camera      │     │ Camera      │
      │ Soil Sensors│     │ Soil Sensors│     │ Soil Sensors│
      │ Env. Sensors│     │ Env. Sensors│     │ Env. Sensors│
      │             │     │             │     │             │
      │ Raspberry Pi│     │ Raspberry Pi│     │ Raspberry Pi│
      │ Local AI    │     │ Local AI    │     │ Local AI    │
      └─────────────┘     └─────────────┘     └─────────────┘
```

Each probe performs sensing and local intelligence independently, allowing the system to scale across heterogeneous field conditions.

---

## ⚙️ Prototype Status

### ✅ Implemented

* Raspberry Pi 4B-based field probe prototype
* Integrated crop imaging
* Soil and environmental sensing
* On-device AI inference
* DINOv2-based visual embeddings
* Prototype-based pest retrieval
* Spherical K-Means prototype memory
* Few-shot pest recognition
* Confidence estimation
* Open-set unknown pest detection
* 25+ pest classes across 10 crops
* Prototype-based addition of new pest classes
* Autonomous sensing and processing workflow

### 🔄 In Development

* ROI extraction
* Background handling
* Vision pre-processing and post-processing
* Improved confidence-based assessment
* Gateway communication
* Field-level multimodal assessment
* Robust sensor handling

### 🔭 Planned

* Disease classification
* Unknown disease detection
* Nutrient-deficiency detection
* Plant growth-stage estimation
* Sensor redundancy
* Multi-probe communication
* Qualcomm edge-AI deployment
* Expanded field validation

---

## 💡 Why Edge AI?

Continuous cloud-based agricultural monitoring can be limited by connectivity, bandwidth, power consumption, and infrastructure availability.

IntelliFarm instead performs computation close to the crop.

**Edge processing provides:**

* Reduced dependence on internet connectivity
* Lower raw-data transmission requirements
* Local decision making
* Reduced communication overhead
* Autonomous operation
* Scalable distributed monitoring

Only relevant information needs to leave the field probe.

---

## 🌱 Expected Impact

IntelliFarm aims to support:

* Earlier pest and disease intervention
* Smarter irrigation decisions
* Reduced unnecessary pesticide and fertilizer use
* Lower agricultural input losses
* Better monitoring of heterogeneous fields
* Improved resilience to droughts, floods, heat waves, excessive rainfall, and other environmental stresses

The system is particularly targeted toward **small and marginal farmers operating in resource- and connectivity-constrained environments**.

---

## 🛠️ Technology Stack

**Edge Hardware**

* Raspberry Pi 4B
* IMX708
* Soil and environmental sensors
* Rechargeable battery and BMS

**Computer Vision / AI**

* Python
* PyTorch
* DINOv2
* Vision embeddings
* Spherical K-Means
* Prototype-based retrieval
* Open-set recognition

**Communication**

* Low-power wireless communication
* Gateway-based architecture
* Direct / multi-hop communication under evaluation

---

## 📁 Repository Structure

The repository is being organized around the major components of the IntelliFarm system:

```text
IntelliFarm/
├── vision/
│   ├── models/
│   ├── retrieval/
│   ├── prototypes/
│   ├── preprocessing/
│   └── inference/
│
├── edge/
│   ├── camera/
│   ├── sensors/
│   ├── inference/
│   ├── communication/
│   └── power/
│
├── hardware/
│   ├── schematics/
│   ├── enclosure/
│   └── components/
│
├── data/
│   └── documentation/
│
├── docs/
│   ├── architecture/
│   ├── deployment/
│   └── experiments/
│
└── README.md
```

The structure will evolve as additional hardware, communication, and computer-vision components are integrated.

---

## 📊 Demonstration

The current prototype demonstrates the **IntelliFarm Pest Retrieval System**, including:

* Crop image input
* Pest retrieval
* Similarity analysis
* Top-K prototype retrieval
* Confidence assessment
* Unknown / novel pest detection

The demonstrated inference runs locally on the Raspberry Pi 4B.

---

## 👥 Team

### AgroInsight

**IntelliFarm — Smart India Hackathon 2026**

Problem Statement: **SIH 26180**

Theme: **Agriculture, FoodTech & Rural Development**

Category: **Hardware**

Team ID: **129026**

---

## 📚 References

* DINOv2 — Learning Robust Visual Features without Supervision
* IP102 — A Large-Scale Benchmark Dataset for Insect Pest Recognition
* Edge AI for Smart Agriculture
* Plantix
* Fermata
* MahaVISTAAR

---

## 🔗 Project

**Repository:** [agroinsight-iitb/IntelliFarm](https://github.com/agroinsight-iitb/IntelliFarm)

---

> **IntelliFarm: Bringing AI closer to the crop.**
