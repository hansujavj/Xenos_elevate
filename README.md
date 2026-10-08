<p align="center">

# 🌱 AgriChain

**Edge AI-Powered Smart Agriculture Advisory & Field Monitoring System**

*Bringing multimodal agricultural intelligence closer to the field with Google Gemma 4, ESP32 IoT sensing, and deterministic safety-aware decision making.*

</p>

<!-- Badges -->
<p align="center">
  <img src="https://img.shields.io/badge/Google-Gemma_4-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Gemma 4"/>
  <img src="https://img.shields.io/badge/Edge_AI-Multimodal-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="Edge AI"/>
  <img src="https://img.shields.io/badge/ESP32-IoT_Sensing-E7352C?style=for-the-badge&logo=espressif&logoColor=white" alt="ESP32"/>
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI"/>
  <img src="https://img.shields.io/badge/React_Native-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React Native"/>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License"/>
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,fastapi,react,typescript,pytorch,postgres,arduino,git,github,docker" alt="Tech Stack"/>
</p>

---

AgriChain is an integrated agriculture platform for rural farmers that unifies **AI-based crop disease diagnosis**, **IoT-driven field monitoring**, **smart irrigation**, **weather intelligence**, and **market insights** into a single coherent system. At its core, **Google Gemma 4** operates as the **Edge AI reasoning layer** — interpreting crop images, farmer inputs, and sensor context to generate structured agricultural recommendations that are validated through a **deterministic Decision / Safety Engine** before reaching the farmer or controlling field hardware.

> **Key Principle:** Gemma 4 provides multimodal reasoning and contextual understanding. Safety-critical actuator decisions (e.g., irrigation pump control) are **always** validated by deterministic threshold logic — never delegated blindly to a language model.

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/hero-banner.png" width="900" alt="AgriChain — Edge AI Smart Agriculture"/>
</p>

---

## Table of Contents

<details>
<summary><strong>Click to expand</strong></summary>

1. [Project Name](#1--project-name)
2. [Problem Statement](#2--problem-statement)
3. [Project Overview](#3--project-overview)
4. [Proposed Solution](#4--proposed-solution)
5. [Objectives](#5--objectives)
6. [Target Users / Use Case](#6--target-users--use-case)
7. [Open-Source AI Technology Selected](#7--open-source-ai-technology-selected)
8. [Why This Technology Was Selected](#8--why-this-technology-was-selected)
9. [AI's Role in the System](#9--ais-role-in-the-system)
10. [System Architecture](#10--system-architecture)
11. [Component-Level Architecture](#11--component-level-architecture)
12. [Data / Information Flow](#12--data--information-flow)
13. [Agentic Workflow](#13--agentic-workflow-if-applicable)
14. [Technology Stack](#14--technology-stack)
15. [Expected Features](#15--expected-features)
16. [Implementation Approach](#16--implementation-approach)
17. [Expected Final Output](#17--expected-final-output)
18. [Future Scope / Scalability](#18--future-scope--scalability)
19. [Open-Source Dependencies / Components](#19--open-source-dependencies--components)
20. [Expected Challenges and Mitigation](#20--expected-challenges-and-mitigation)
21. [Quick Start](#-quick-start)
22. [Project Structure](#-project-structure)
23. [Security & Safety](#-security--safety)
24. [Testing](#-testing)
25. [Screenshots & Demo](#-screenshots--demo)
26. [Demo Videos](#-demo)
27. [Team](#-team)
28. [Why AgriChain?](#-why-agrichain)

</details>

---

## 1. 🌱 Project Name

<h1 align="center">AgriChain</h1>
<h3 align="center"><em>Edge AI-Powered Smart Agriculture Advisory & Field Monitoring System</em></h3>

<br>

AgriChain is an end-to-end agriculture platform designed for **rural farmers** who lack timely access to crop health expertise, localized weather guidance, market intelligence, and efficient irrigation management. The system combines **Google Gemma 4** multimodal Edge AI inference with **ESP32-based IoT field sensing** and a **deterministic Decision / Safety Engine** to deliver actionable, context-aware agricultural recommendations — even in environments with limited or intermittent internet connectivity.

```mermaid
flowchart TD
    AC["AGRICHAIN"] --- FI & IOT

    subgraph FI["Farmer Input"]
        IMG["Image / Voice"]
    end

    subgraph IOT["Field IoT"]
        ESP_S["ESP32 Sensors"]
    end

    IMG --> GW
    ESP_S --> GW

    GW["EDGE AI GATEWAY"]
    GW --> G4["Gemma 4"]
    G4 --> MR["Multimodal Reasoning"]
    MR --> DSE["Decision / Safety Engine"]
    DSE --> FA["Farmer Advisory"]
    DSE --> IRR["Irrigation"]
    IRR --> RP["Relay / Pump"]

    style AC fill:#2E7D32,color:#fff,stroke:#1B5E20
    style GW fill:#1565C0,color:#fff
    style G4 fill:#4285F4,color:#fff
    style DSE fill:#34A853,color:#fff
```

---

## 2. 📋 Problem Statement

Rural farmers face a constellation of interconnected challenges that compound crop losses, waste water, and reduce livelihoods:

| Problem | Impact |
|:--------|:-------|
| **Delayed crop disease detection** | By the time visible symptoms are severe enough for an untrained eye, the disease has often spread, reducing yields significantly |
| **Lack of localized agricultural advice** | Generic recommendations from distant experts or government advisories do not account for field-specific soil, weather, and crop conditions |
| **Generalized weather information** | Broad regional forecasts fail to inform hyper-local irrigation and protection decisions |
| **Limited access to market information** | Farmers sell at sub-optimal prices due to lack of timely, localized market data |
| **Inefficient irrigation** | Manual or timer-based irrigation leads to over-irrigation (wasting water, damaging roots) or under-irrigation (reducing yields) |
| **Fragmented agricultural tools** | Disease identification, weather, market prices, and irrigation are handled by separate, disconnected tools — if available at all |
| **Limited access to expert guidance** | Agricultural extension officers are stretched thin; expert consultations are costly and delayed |
| **Connectivity constraints** | Cloud-dependent solutions fail in rural areas with poor or intermittent internet access |

**The core problem:** Rural farmers need a unified, intelligent, field-aware agricultural advisory system that works reliably at the edge — not a collection of disconnected cloud services that require constant connectivity.

---

## 3. 🔍 Project Overview

AgriChain is a **unified agricultural intelligence ecosystem** that consolidates four critical agricultural functions into a single platform, powered by **Gemma 4 Edge AI** and **ESP32 IoT sensing**.

```mermaid
flowchart TD
    F["👨‍🌾 Farmer"] --> AC["🌱 AgriChain"]
    AC --> EAI["🧠 Edge AI"]
    AC --> IoT["📡 IoT"]
    AC --> EXT["☁️ External Data"]
    EAI --> IR["📋 Intelligent Recommendations"]
    IoT --> IR
    EXT --> IR
    IR --> FA["✅ Farmer Action"]

    style AC fill:#2E7D32,color:#fff,stroke:#1B5E20
    style EAI fill:#1565C0,color:#fff
    style IR fill:#FF8F00,color:#fff
```

### The Four Primary Modules

<table>
<tr>
<td width="25%" align="center">
<h4>🔬 Crop Clinic</h4>
<p>AI-powered crop disease diagnosis through multimodal analysis of crop images, farmer descriptions, and field context. Gemma 4 interprets visual symptoms, estimates severity, and generates treatment recommendations.</p>
</td>
<td width="25%" align="center">
<h4>🌦 Weather Intelligence</h4>
<p>Localized weather alerts and weather-aware agricultural advisories. Integrates forecast data with field conditions to produce actionable guidance on irrigation timing, crop protection, and field operations.</p>
</td>
<td width="25%" align="center">
<h4>📈 Market Insights</h4>
<p>Crop price information and market intelligence to help farmers make informed selling decisions. Aggregates price data from relevant markets to improve price realization.</p>
</td>
<td width="25%" align="center">
<h4>💧 Smart Irrigation Assistant</h4>
<p>Real-time soil moisture monitoring via ESP32 sensors, combined with weather context and AI-driven recommendations. Relay-based pump control with deterministic safety validation.</p>
</td>
</tr>
</table>

Each module feeds into and draws from a shared intelligence layer — Gemma 4 on the Edge AI Gateway — ensuring that recommendations are **contextually coherent** across all four functions. A crop disease diagnosis, for example, can inform irrigation adjustments; weather data influences both disease risk and irrigation scheduling.

---

## 4. 💡 Proposed Solution

AgriChain proposes an integrated system where:

1. **The farmer** interacts through a mobile application — uploading crop images, providing voice/text descriptions, and viewing recommendations
2. **ESP32 Sensor Nodes** continuously monitor field conditions (soil moisture, temperature, humidity, rainfall)
3. **The Edge AI Gateway** running **Gemma 4** receives both farmer inputs and sensor context, performing multimodal reasoning to generate structured agricultural insights
4. **A deterministic Decision / Safety Engine** validates AI-generated recommendations before they reach the farmer or trigger any actuator
5. **Actuator control** (relay-based water pump) operates only after deterministic threshold validation — never directly from raw LLM output

```mermaid
flowchart TB
    subgraph Farmer["👨‍🌾 Farmer Interaction"]
        A[Crop Image Capture] --> D
        B[Voice / Text Description] --> D
        C[Mobile / Web App] --> D
        D[AgriChain Application]
    end

    subgraph Field["🌾 Field IoT Layer"]
        E[ESP32 Sensor Node]
        F[Soil Moisture Sensor]
        G[DHT22 — Temp / Humidity]
        H[Rain Sensor]
        F --> E
        G --> E
        H --> E
    end

    subgraph Backend["⚙️ AgriChain Backend"]
        I[API Gateway — FastAPI]
        J[Weather API Integration]
        K[Market Data Integration]
        L[Database — PostgreSQL]
    end

    subgraph EdgeAI["🧠 Edge AI Gateway"]
        M[Gemma 4 — Multimodal Inference]
        N[Prompt Construction & Context Assembly]
        O[Structured Output Parser]
    end

    subgraph Safety["🛡️ Decision / Safety Engine"]
        P[Threshold Validation]
        Q[Rule Engine]
        R[Safety Checks]
    end

    subgraph Output["📤 Output Layer"]
        S[Farmer Advisory & Notifications]
        T[Irrigation Recommendation]
        U[Relay Control Signal]
        V[Water Pump]
    end

    D --> I
    E --> I
    I --> N
    J --> I
    K --> I
    N --> M
    M --> O
    O --> P
    P --> Q
    Q --> R
    R --> S
    R --> T
    T --> U
    U --> V
    I --> L
```

> **Critical Design Decision:** The Decision / Safety Engine sits between Gemma 4's output and any physical actuator. AI-generated irrigation recommendations are treated as **advisory input** to the deterministic engine, which applies threshold validation, rule checks, and safety constraints before permitting pump activation.

---

## 5. 🎯 Objectives

- **Early crop disease detection** — enable farmers to identify diseases before widespread damage through AI-powered image analysis
- **Contextual agricultural advisory** — provide recommendations that account for the specific field's soil, weather, crop, and sensor conditions
- **Continuous field-level monitoring** — deploy ESP32 sensor nodes for real-time soil moisture, temperature, humidity, and rainfall tracking
- **Efficient, sensor-informed irrigation** — replace manual guesswork with data-driven irrigation recommendations
- **Water conservation** — reduce over-irrigation through precise moisture monitoring and intelligent scheduling
- **Localized decision support** — deliver advice relevant to the farmer's specific location, crop, and conditions
- **Improved farmer awareness** — surface weather alerts, market prices, and crop health information in a unified interface
- **Reduced dependence on continuous cloud inference** — run Gemma 4 on an Edge AI Gateway for low-latency, connectivity-resilient operation
- **Scalable rural deployment** — design an architecture that can expand from a single farm to village and district-level deployments

---

## 6. 👥 Target Users / Use Case

### Primary User Segments

| User Segment | Primary Need | AgriChain Capability |
|:-------------|:-------------|:---------------------|
| **Rural Farmers** | Timely crop disease identification, irrigation guidance, market prices | Crop Clinic diagnosis, Smart Irrigation recommendations, Market Insights |
| **Agricultural Extension Workers** | Field-level data to support farmer advisory | Sensor dashboards, AI-generated diagnostic reports, historical field data |
| **Village Committees / Gram Panchayat** | Community-level agricultural monitoring, resource optimization | Aggregated field data, water usage insights, crop health summaries |
| **Agricultural Support Organizations** | Scalable farmer outreach and decision support | Platform data for program design, regional crop health patterns |
| **Educational / Research Institutions** | Field data for agricultural research, AI model improvement | Anonymized sensor and diagnostic data, model performance feedback |

### Practical Use Case Scenarios

<details>
<summary><strong>Scenario 1 — Diseased Crop Diagnosis</strong></summary>

A farmer notices yellowing leaves on their tomato crop. They open the AgriChain app, capture a photo, and optionally describe: *"Leaves turning yellow from edges, some brown spots."* Gemma 4 on the Edge AI Gateway interprets the image alongside the farmer's description and current field conditions (soil moisture: adequate, recent rainfall: none, temperature: 34°C). The model identifies a likely fungal infection, explains visible symptoms, estimates moderate severity, and recommends specific treatment steps. The recommendation passes through the Decision / Safety Engine before being displayed to the farmer.
</details>

<details>
<summary><strong>Scenario 2 — Dry Soil Detection & Irrigation</strong></summary>

ESP32 sensors report soil moisture dropping below the configured threshold for the planted crop. The Edge AI Gateway receives this context alongside recent weather data (no rain forecast for 72 hours). Gemma 4 generates an irrigation recommendation considering crop stage, soil type, and weather outlook. The Decision / Safety Engine validates the recommendation against threshold rules and, if approved, sends a relay activation signal to the water pump. The farmer is notified of the action taken.
</details>

<details>
<summary><strong>Scenario 3 — Weather-Aware Irrigation Adjustment</strong></summary>

Weather intelligence indicates heavy rainfall expected within 6 hours. Even though soil moisture is currently below threshold, the system defers irrigation to avoid waterlogging. The farmer receives a notification explaining the decision.
</details>

<details>
<summary><strong>Scenario 4 — Farmer Voice/Text Query</strong></summary>

A farmer asks via voice: *"My cotton leaves are curling. What should I do?"* The voice input is transcribed and, combined with the farmer's registered crop type and current sensor readings, sent to Gemma 4. The model provides a contextual response explaining possible causes (pest infestation, heat stress, nutrient deficiency) and suggested next steps.
</details>

<details>
<summary><strong>Scenario 5 — Sensor-Driven Recommendation</strong></summary>

Continuous monitoring detects a sustained rise in humidity combined with moderate temperatures — conditions favorable for certain fungal diseases. The system proactively alerts the farmer to inspect their crop and suggests preventive measures.
</details>

---

## 7. 🤖 Open-Source AI Technology Selected

### Google Gemma 4

**Gemma 4** is the **primary Edge AI model** powering AgriChain's agricultural intelligence layer. It is not used as a general-purpose chatbot or a thin API wrapper — it serves as the **multimodal reasoning engine** that interprets complex agricultural contexts and produces structured, actionable insights.

<table>
<tr>
<td width="50%">

#### Gemma 4 in AgriChain

- **Multimodal agricultural reasoning** — processes crop images alongside textual/voice descriptions and sensor context simultaneously
- **Crop image understanding** — interprets visual symptoms of disease, nutrient deficiency, pest damage, and growth anomalies
- **Contextual interpretation** — combines farmer input with field sensor data (soil moisture, temperature, humidity, rain) to produce field-aware analysis
- **Farmer interaction** — generates explanations in farmer-friendly language, not technical jargon
- **Structured recommendation generation** — outputs formatted, parseable recommendations that feed into the Decision / Safety Engine

</td>
<td width="50%">

```mermaid
flowchart TD
    CI["📸 Crop Image"] --> G4
    FI["🗣️ Farmer Input — Voice/Text"] --> G4
    FC["📡 Field Context — Sensors"] --> G4

    G4["🧠 Gemma 4 — Edge AI"]
    G4 --> SAI

    subgraph SAI["Structured Agricultural Insight"]
        S1["Disease / Condition"]
        S2["Severity Estimate"]
        S3["Symptom Explanation"]
        S4["Treatment Recommendation"]
        S5["Irrigation Guidance"]
    end

    SAI --> DSL

    subgraph DSL["🛡️ Decision / Safety Layer"]
        D1["Threshold Validation"]
        D2["Rule Checks"]
        D3["Actuator Safety"]
    end

    style G4 fill:#4285F4,color:#fff
    style DSL fill:#34A853,color:#fff
```

</td>
</tr>
</table>

> **Gemma 4 is the reasoning layer of AgriChain.** It interprets what sensors measure and what farmers observe, producing structured intelligence that the deterministic safety layer can then validate and act upon.

---

## 8. 🧪 Why This Technology Was Selected

Gemma 4 was selected because AgriChain requires **intelligence close to the field, not only a remote cloud chatbot.** The engineering rationale:

| Selection Criterion | Justification |
|:--------------------|:--------------|
| **Open-weight ecosystem** | Gemma 4's open-weight availability enables local deployment, inspection, and customization without vendor lock-in |
| **Multimodal capability** | Natively processes both images and text — essential for combining crop photos with farmer descriptions and sensor context |
| **Edge deployment suitability** | Designed with efficiency considerations that make edge gateway deployment practical, unlike models that require massive cloud infrastructure |
| **Reduced cloud dependence** | Rural deployment cannot rely on constant, high-bandwidth cloud connectivity; edge inference provides resilience |
| **Privacy-aware processing** | Farmer data (crop images, field conditions, queries) can be processed locally without transmitting sensitive information to external cloud services |
| **Low-latency inference** | Edge deployment eliminates round-trip network latency — critical when a farmer is standing in a field waiting for a diagnosis |
| **Offline/poor-connectivity operation** | The Edge AI Gateway can continue functioning during connectivity outages, with synchronization when connectivity resumes |
| **Contextual reasoning capability** | Goes beyond simple classification — can explain symptoms, reason about causality, and generate contextual recommendations |
| **Visual + contextual fusion** | Can interpret a crop image not in isolation but together with soil moisture readings, weather data, and farmer observations |

<blockquote>
<strong>Why not a cloud-only approach?</strong>
<br><br>
A cloud-only AI service would fail when the farmer's 2G connection drops, introduce unacceptable latency for field-side diagnosis, continuously transmit sensitive farm data to external servers, and incur per-query costs that are unsustainable for smallholder farmers. Gemma 4 on an Edge AI Gateway addresses all four constraints.
</blockquote>

---

## 9. 🧠 AI's Role in the System

### Gemma 4: The Reasoning Layer

Gemma 4 handles the **interpretation and reasoning** components of AgriChain. Deterministic code handles everything that requires precision, safety, or direct hardware interaction.

#### AI Function Mapping

| AI Function | Input | Gemma 4's Role | Output |
|:------------|:------|:---------------|:-------|
| **Crop Disease Diagnosis** | Crop image + farmer description + field context | Multimodal interpretation — identifies visible disease symptoms, correlates with environmental conditions | Disease/condition identification, severity estimate, symptom explanation |
| **Treatment Recommendation** | Diagnosis result + crop type + field context | Contextual reasoning — generates appropriate treatment steps considering crop stage and conditions | Structured treatment plan with prioritized steps |
| **Farmer Query Response** | Voice/text query + crop context + sensor data | Natural language understanding + contextual reasoning | Farmer-friendly explanation and actionable guidance |
| **Irrigation Advisory** | Soil moisture + weather forecast + crop type + growth stage | Contextual reasoning — evaluates water needs considering multiple variables | Irrigation recommendation (timing, duration, urgency) |
| **Proactive Alert Generation** | Sensor trends + weather data + crop vulnerability | Pattern interpretation — identifies conditions favorable for disease or stress | Early warning with preventive recommendations |
| **Field Context Synthesis** | All available sensor readings + recent history | Holistic field assessment combining multiple data streams | Unified field health summary |

#### Clear Separation of Responsibilities

<table>
<tr>
<th width="50%">🧠 Gemma 4 (AI Reasoning)</th>
<th width="50%">⚙️ Deterministic Code (Rules & Safety)</th>
</tr>
<tr>
<td>

- Interprets crop images for visual symptoms
- Reasons about disease causality
- Generates farmer-friendly explanations
- Synthesizes multi-source context
- Produces structured recommendations
- Answers farmer questions contextually

</td>
<td>

- Validates sensor thresholds
- Enforces irrigation safety limits
- Controls relay/pump actuators
- Performs numerical calculations
- Manages sensor calibration ranges
- Handles authentication and authorization
- Applies rate limits and safety overrides

</td>
</tr>
</table>

```mermaid
flowchart LR
    subgraph AI["Gemma 4 — Reasoning"]
        A1[Image Interpretation]
        A2[Contextual Reasoning]
        A3[Recommendation Generation]
        A4[Explanation Synthesis]
    end

    subgraph DET["Deterministic — Rules & Safety"]
        D1[Threshold Validation]
        D2[Safety Constraints]
        D3[Actuator Control]
        D4[Numerical Computation]
    end

    A3 -->|Structured Advisory| D1
    D1 --> D2
    D2 -->|Approved| D3
    D2 -->|Rejected / Modified| NOTIFY[Farmer Notification]
```

> **Design Principle:** Gemma 4 is never given direct control over physical actuators. Its output is always treated as a **structured recommendation** that must pass through the Decision / Safety Engine before any action is taken.

---

## 10. 🏗 System Architecture

```mermaid
flowchart TB
    subgraph Farmer["👨‍🌾 Farmer Layer"]
        FA[Crop Image]
        FB[Voice / Text Input]
        FC[Mobile / Web Application]
    end

    subgraph Cloud["☁️ Cloud Services"]
        CW[Weather API]
        CM[Market Data API]
    end

    subgraph Backend["⚙️ AgriChain Backend"]
        BA[FastAPI Gateway]
        BD[PostgreSQL Database]
        BN[Notification Service]
        BA <--> BD
    end

    subgraph Edge["🧠 Edge AI Gateway"]
        EA[Context Assembler]
        EB["Gemma 4 — Multimodal Inference"]
        EC[Structured Output Parser]
        EA --> EB
        EB --> EC
    end

    subgraph Safety["🛡️ Decision / Safety Engine"]
        SA[Threshold Validator]
        SB[Rule Engine]
        SC[Safety Override]
        SA --> SB
        SB --> SC
    end

    subgraph IoT["📡 ESP32 Sensor Node"]
        IA[Soil Moisture Sensor]
        IB[DHT22 — Temp/Humidity]
        IC[Rain Sensor]
        ID[ESP32 Microcontroller]
        IE[Relay Module]
        IF[Water Pump]
        IA --> ID
        IB --> ID
        IC --> ID
        IE --> IF
    end

    FA --> FC
    FB --> FC
    FC --> BA
    CW --> BA
    CM --> BA
    BA --> EA
    ID -->|Sensor Data| BA
    EC --> SA
    SC -->|Farmer Advisory| BN
    SC -->|Irrigation Command| ID
    ID --> IE
    BN --> FC
```

### Architecture Highlights

- **ESP32** = low-power field sensing and actuator/control node. It does **not** run Gemma 4.
- **Edge AI Gateway** = the compute device (e.g., a local server, Jetson-class device, or capable SBC) that runs Gemma 4 inference.
- **Decision / Safety Engine** = deterministic validation layer between AI output and any action.
- **Backend** = orchestrates data flow, integrates external APIs, manages state and notifications.

---

## 11. 📦 Component-Level Architecture

| Component | Responsibility | Input | Output |
|:----------|:---------------|:------|:-------|
| **Mobile / Web Frontend** | Farmer interface — image capture, voice/text input, dashboard display | Farmer interactions | API requests to backend |
| **FastAPI Backend** | API gateway, data orchestration, external API integration, state management | Frontend requests, sensor data, external API responses | Inference payloads, farmer responses, database records |
| **Gemma 4 Edge AI** | Multimodal reasoning — crop diagnosis, contextual interpretation, recommendation generation | Assembled context (image + text + sensor data) | Structured agricultural insight (JSON) |
| **Decision / Safety Engine** | Validates AI recommendations against thresholds, rules, and safety constraints | Structured AI output + current sensor readings | Approved/modified recommendations, actuator commands |
| **ESP32 Microcontroller** | Field-level data acquisition and actuator control | Analog/digital sensor signals | Sensor readings (via MQTT/HTTP), relay activation |
| **Soil Moisture Sensor** | Measures volumetric water content in soil | Analog voltage (soil resistance) | Moisture percentage / raw analog value |
| **DHT22 (Temp/Humidity)** | Measures ambient temperature and relative humidity | Environmental conditions | Temperature (°C), Humidity (%) |
| **Rain Sensor** | Detects rainfall presence and approximate intensity | Raindrop contact on sensor surface | Rain detected (boolean), intensity estimate |
| **Relay Module** | Electrically switches the water pump on/off | Digital control signal from ESP32 | Circuit open/close for pump power |
| **Water Pump** | Irrigates the field | Electrical power via relay | Water flow to field |
| **PostgreSQL Database** | Persistent storage for sensor history, diagnoses, user data, recommendations | Structured records from backend | Query results |
| **Weather API** | Provides localized weather forecasts and alerts | Location coordinates, API key | Forecast data (JSON) |
| **Market Data API** | Provides crop market prices from relevant mandis/markets | Crop type, location | Price data (JSON) |
| **Notification Service** | Delivers alerts and recommendations to the farmer | Triggered events, recommendations | Push notifications, in-app alerts |

```mermaid
flowchart LR
    subgraph HW["Hardware Layer"]
        SM[Soil Moisture]
        DHT[DHT22]
        RAIN[Rain Sensor]
        ESP[ESP32]
        RELAY[Relay]
        PUMP[Water Pump]
        SM --> ESP
        DHT --> ESP
        RAIN --> ESP
        ESP --> RELAY --> PUMP
    end

    subgraph SW["Software Layer"]
        FE[Frontend App]
        BE[FastAPI Backend]
        DB[(PostgreSQL)]
        NS[Notification Service]
        BE <--> DB
        BE --> NS --> FE
    end

    subgraph AI["Intelligence Layer"]
        CTX[Context Assembler]
        G4["Gemma 4"]
        DSE["Decision / Safety Engine"]
        CTX --> G4 --> DSE
    end

    subgraph EXT["External Data"]
        WX[Weather API]
        MK[Market API]
    end

    FE --> BE
    ESP -->|Sensor Data| BE
    BE --> CTX
    WX --> BE
    MK --> BE
    DSE -->|Advisory| BE
    DSE -->|Control Signal| ESP
```

---

## 12. 🔄 Data / Information Flow

### Crop Diagnosis Flow

```mermaid
flowchart TD
    A["📸 Farmer captures crop image"] --> B["📱 App sends image + text/voice to backend"]
    B --> C["⚙️ Backend assembles inference payload"]
    C --> D["📡 Backend queries current sensor readings from ESP32"]
    D --> E["🧠 Edge AI Gateway receives context"]
    E --> F["🧠 Gemma 4 multimodal inference"]
    F --> G["📋 Structured result: disease, severity, symptoms, recommendations"]
    G --> H["🛡️ Decision / Safety Engine evaluates result"]
    H --> I["✅ Recommendation validated and formatted"]
    I --> J["📱 Farmer receives diagnosis + actionable recommendations"]

    style F fill:#4285F4,color:#fff
    style H fill:#34A853,color:#fff
```

### IoT Sensor → Irrigation Flow

```mermaid
flowchart TD
    A["📡 ESP32 reads sensors"] --> B["📊 Soil Moisture / Temp / Humidity / Rain"]
    B --> C["⚙️ Sensor data sent to Backend"]
    C --> D["🧠 Edge AI Gateway receives field context"]
    D --> E["🧠 Gemma 4 evaluates irrigation need"]
    E --> F["📋 Irrigation recommendation generated"]
    F --> G["🛡️ Decision / Safety Engine"]
    G --> H{"Threshold & Safety Check"}
    H -->|Pass| I["✅ Relay activation signal sent to ESP32"]
    H -->|Fail| J["⚠️ Recommendation logged, farmer notified"]
    I --> K["💧 Water pump activates"]
    K --> L["📡 ESP32 continues monitoring"]
    L --> A

    style E fill:#4285F4,color:#fff
    style G fill:#34A853,color:#fff
    style H fill:#FBBC04,color:#000
```

### Combined Data Flow

```mermaid
sequenceDiagram
    participant F as 👨‍🌾 Farmer
    participant App as 📱 Mobile App
    participant BE as ⚙️ Backend
    participant ESP as 📡 ESP32
    participant Edge as 🧠 Edge AI Gateway
    participant G4 as Gemma 4
    participant DSE as 🛡️ Decision Engine
    participant Relay as ⚡ Relay
    participant Pump as 💧 Pump

    F->>App: Capture crop image + description
    App->>BE: POST /diagnose {image, text, location}
    BE->>ESP: GET /sensors (current readings)
    ESP-->>BE: {moisture: 28%, temp: 33°C, humidity: 65%, rain: false}
    BE->>Edge: Assembled context payload
    Edge->>G4: Multimodal inference request
    G4-->>Edge: Structured diagnosis + recommendations
    Edge-->>BE: Parsed result
    BE->>DSE: Validate recommendations
    DSE-->>BE: Approved advisory + irrigation recommendation
    BE-->>App: Diagnosis result + advisory
    App-->>F: Display diagnosis, severity, treatment steps

    Note over DSE, Relay: If irrigation recommended and approved:
    DSE->>ESP: Irrigation command (validated)
    ESP->>Relay: Activate
    Relay->>Pump: Power ON
    Note over Pump: Irrigation for validated duration
    ESP->>Relay: Deactivate after duration
    Relay->>Pump: Power OFF
    ESP-->>BE: Irrigation complete confirmation
    BE-->>App: Irrigation status update
    App-->>F: Notification: Irrigation completed
```

---

## 13. 🔁 Agentic Workflow (if applicable)

AgriChain implements an **agentic-style decision workflow** — a structured observe-interpret-reason-validate-act loop — rather than a fully autonomous agent. This workflow enables proactive, context-aware behavior while maintaining deterministic safety control over all physical actions.

> **Important:** This is not a fully autonomous AI agent. Safety-critical actions (actuator control, irrigation execution) are **always** governed by the deterministic Decision / Safety Engine. The "agentic" aspect refers to the structured decision loop, not unsupervised autonomous operation.

```mermaid
flowchart TD
    A["🔍 OBSERVE"] --> B["🧠 INTERPRET"]
    B --> C["💡 REASON"]
    C --> D["✅ VALIDATE"]
    D --> E["📤 RECOMMEND"]
    E --> F{"Safety-Critical Action?"}
    F -->|Yes| G["🛡️ Decision / Safety Engine"]
    G --> H{"Approved?"}
    H -->|Yes| I["⚡ ACT — Execute via ESP32"]
    H -->|No| J["⚠️ Log & Notify Farmer"]
    F -->|No| K["📱 Advisory Delivered to Farmer"]
    I --> L["🔄 FEEDBACK — New sensor readings"]
    J --> L
    K --> L
    L --> A

    style A fill:#E8F5E9
    style B fill:#E3F2FD
    style C fill:#FFF3E0
    style D fill:#F3E5F5
    style G fill:#34A853,color:#fff
```

### Workflow Stages

| Stage | Description | Responsible Component |
|:------|:------------|:----------------------|
| **OBSERVE** | Collect sensor readings (soil moisture, temp, humidity, rain), farmer inputs (image, text/voice), weather forecasts, and market data | ESP32 Sensor Node, Mobile App, External APIs |
| **INTERPRET** | Gemma 4 processes multimodal inputs — understanding crop images, parsing farmer descriptions, contextualizing sensor data | Gemma 4 on Edge AI Gateway |
| **REASON** | Determine likely agricultural issue: disease identification, irrigation need, weather risk, or market opportunity | Gemma 4 contextual reasoning |
| **VALIDATE** | Apply deterministic rules, threshold checks, and safety constraints to the AI-generated recommendation | Decision / Safety Engine |
| **RECOMMEND** | Deliver validated, farmer-friendly advisory through the mobile application | Backend + Notification Service |
| **ACT** | For approved actuator operations: execute relay control for irrigation pump | ESP32 + Relay (only after deterministic approval) |
| **FEEDBACK** | New sensor readings after action confirm effect; loop restarts | ESP32 continuous monitoring |

---

## 14. 🛠 Technology Stack

### AI / ML

| Technology | Role |
|:-----------|:-----|
| **Google Gemma 4** | Core multimodal Edge AI model — crop image analysis, contextual reasoning, recommendation generation |
| **PyTorch** | Model loading, inference runtime, tensor operations |
| **Transformers (Hugging Face)** | Model interface and tokenization |
| **Pillow / OpenCV** | Image preprocessing for inference pipeline |

### Edge AI

| Technology | Role |
|:-----------|:-----|
| **Edge AI Gateway** | Local compute device running Gemma 4 inference (e.g., NVIDIA Jetson, capable SBC, or local server) |
| **Google AI Edge / compatible runtime** | Optimized inference serving for edge deployment |

### Backend

| Technology | Role |
|:-----------|:-----|
| **Python 3.10+** | Primary backend language |
| **FastAPI** | REST API framework — async, high-performance |
| **SQLAlchemy** | ORM for database interactions |
| **Pydantic** | Request/response validation and structured output parsing |
| **MQTT / HTTP** | ESP32 ↔ Backend communication |

### Frontend

| Technology | Role |
|:-----------|:-----|
| **React Native** | Cross-platform mobile application for farmers |
| **React** | Web dashboard for monitoring and administration |
| **TypeScript** | Type-safe frontend development |

### IoT / Hardware

| Component | Specification | Role |
|:----------|:-------------|:-----|
| **ESP32** | Dual-core MCU, Wi-Fi/BLE | Field sensor node + actuator controller |
| **Soil Moisture Sensor** | Capacitive / Resistive | Measures soil water content |
| **DHT22** | Digital temp/humidity sensor | Ambient temperature and humidity |
| **Rain Sensor** | Resistive rain detection module | Rainfall detection |
| **Relay Module** | 5V single-channel relay | Electrically switches water pump |
| **Water Pump** | 12V DC submersible / motor pump | Field irrigation |

### Data & Infrastructure

| Technology | Role |
|:-----------|:-----|
| **PostgreSQL** | Primary database for sensor history, diagnoses, user data |
| **Docker** | Containerization for backend and Edge AI services |
| **Git / GitHub** | Version control and collaboration |

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,fastapi,react,typescript,pytorch,postgres,arduino,docker,git,github" alt="Core Tech Stack"/>
</p>

---

## 15. ✨ Expected Features

### 🤖 AI Features
- **Gemma 4 crop image analysis** — multimodal interpretation of crop photos for disease/condition identification
- **Multimodal farmer interaction** — processes combined image + voice/text + sensor context for holistic understanding
- **Crop disease reasoning** — explains visible symptoms, correlates with environmental conditions, identifies likely causes
- **Severity assessment** — estimates disease/condition severity based on visual and contextual indicators
- **Contextual recommendations** — generates treatment and management recommendations tailored to specific field conditions
- **Proactive alerts** — identifies risk conditions from sensor trends and weather data before visible symptoms appear

### 🌱 Agriculture
- **Crop Clinic** — unified interface for disease diagnosis, treatment guidance, and crop health monitoring
- **Crop monitoring history** — tracks diagnoses, treatments, and outcomes over time
- **Treatment recommendations** — step-by-step treatment plans with contextual adjustments
- **Crop advisory** — general agricultural guidance based on crop type, growth stage, and conditions

### 💧 Smart Irrigation
- **Real-time soil moisture monitoring** — continuous ESP32 sensor readings displayed on dashboard
- **AI-informed irrigation recommendations** — Gemma 4 considers soil, weather, and crop context
- **Deterministic safety validation** — all pump control passes through threshold and rule checks
- **Relay-based pump control** — ESP32 activates/deactivates water pump via relay module
- **Irrigation logging** — records all irrigation events, durations, and triggering conditions

### 🌦 Weather Intelligence
- **Localized weather information** — forecasts relevant to the farmer's specific location
- **Rainfall alerts** — advance notification of expected precipitation
- **Weather-aware agricultural recommendations** — irrigation and crop protection adjusted for forecast conditions

### 📈 Market Insights
- **Crop price information** — current market prices from relevant local mandis/markets
- **Market trends** — price movement information to support selling decisions
- **Selling guidance** — contextual advice on market timing

### 📱 User Experience
- **Farmer-friendly mobile interface** — simple, intuitive design with vernacular-friendly layouts
- **Plain-language explanations** — AI-generated text written for farmers, not agronomists
- **Push notifications** — alerts for disease risks, irrigation events, weather warnings, market updates
- **Unified dashboard** — all four modules accessible from a single home screen

---

## 16. 📅 Implementation Approach

| Phase | Focus | Expected Deliverables |
|:------|:------|:---------------------|
| **Phase 1** — Requirement Analysis | Define detailed requirements, finalize sensor specifications, identify target crops and regions | Requirements document, crop/disease scope, hardware BOM, API specifications |
| **Phase 2** — IoT Hardware Prototype | Assemble and test ESP32 sensor node with soil moisture, DHT22, rain sensor, and relay | Working sensor node prototype, calibrated sensor readings, relay-controlled pump operation |
| **Phase 3** — Backend & Database | Set up FastAPI server, PostgreSQL database, MQTT/HTTP communication with ESP32 | API endpoints for sensor data ingestion, database schema, ESP32 ↔ backend communication |
| **Phase 4** — Gemma 4 Edge AI Integration | Deploy Gemma 4 on Edge AI Gateway, build inference pipeline, implement prompt engineering for agricultural context | Working inference pipeline, structured output parsing, latency benchmarks |
| **Phase 5** — Crop Clinic | Build crop image capture, diagnosis workflow, treatment recommendation display, history tracking | Functional Crop Clinic module in mobile app, end-to-end diagnosis flow |
| **Phase 6** — Smart Irrigation Integration | Connect sensor data → Gemma 4 → Decision / Safety Engine → ESP32 relay control | Automated irrigation recommendations, deterministic safety validation, pump control |
| **Phase 7** — Weather & Market Integration | Integrate weather API and market data API, build corresponding UI modules | Weather alerts, forecast display, market price dashboard, weather-aware recommendations |
| **Phase 8** — Testing & Field Validation | End-to-end testing, sensor accuracy validation, inference quality review, field trials | Test reports, identified issues, performance documentation, field trial observations |

---

## 17. 📋 Expected Final Output

### Farmer Application
- **Dashboard** — unified view of field health, recent alerts, sensor status, and quick actions
- **Crop Clinic** — image-based diagnosis with severity, explanation, and treatment recommendations
- **Recommendations Feed** — chronological list of AI-generated and rule-based advisories
- **Weather Module** — localized forecast, rainfall alerts, weather-aware guidance
- **Market Module** — crop prices, market trends, selling guidance
- **Irrigation Status** — current soil moisture, irrigation history, upcoming recommendations

### Edge AI Demonstration
- Farmer submits crop image → Gemma 4 performs multimodal inference → structured diagnosis returned → reasoning/explanation displayed → treatment recommendation generated

### Hardware Demonstration
- ESP32 sensor node reporting live soil moisture, temperature, humidity, and rain detection
- Relay activation triggered by validated irrigation recommendation
- Pump operation and automatic deactivation after configured duration

### End-to-End Demonstration

```mermaid
sequenceDiagram
    participant Farmer as 👨‍🌾 Farmer
    participant App as 📱 App
    participant Backend as ⚙️ Backend
    participant EdgeGW as 🧠 Edge Gateway
    participant Gemma as Gemma 4
    participant DSE as 🛡️ Safety Engine
    participant ESP as 📡 ESP32
    participant Relay as ⚡ Relay
    participant Pump as 💧 Pump

    Farmer->>App: Takes crop photo, describes symptoms
    App->>Backend: Sends image + description + location
    Backend->>ESP: Requests current sensor data
    ESP-->>Backend: Soil: 25%, Temp: 35°C, Humidity: 60%, Rain: No
    Backend->>EdgeGW: Assembled multimodal context
    EdgeGW->>Gemma: Inference request
    Gemma-->>EdgeGW: Diagnosis: Early Blight, Severity: Moderate
    EdgeGW-->>Backend: Structured result + recommendations
    Backend->>DSE: Validate recommendations
    DSE-->>Backend: Advisory approved, irrigation recommended
    Backend-->>App: Full diagnosis + advisory + irrigation status
    App-->>Farmer: Displays diagnosis, treatment, irrigation plan

    Note over DSE, ESP: Irrigation execution (if approved)
    DSE->>ESP: Validated irrigation command
    ESP->>Relay: Activate
    Relay->>Pump: ON for 15 minutes
    Note over Pump: Irrigating...
    ESP->>Relay: Deactivate
    Relay->>Pump: OFF
    ESP-->>Backend: Irrigation complete
    Backend-->>App: Status: Irrigation completed
    App-->>Farmer: ✅ Field irrigated — 15 min cycle complete
```

---

## 18. 🚀 Future Scope / Scalability

### Feature Extensions

- **Additional crop varieties** — expand disease and advisory knowledge to cover more crops and regional varieties
- **Expanded disease classes** — incrementally add more disease/pest/deficiency conditions with farmer feedback
- **Multilingual / local-language interaction** — voice and text in regional languages (Hindi, Marathi, Telugu, etc.)
- **Additional sensor types** — light intensity, leaf wetness, soil pH, nutrient sensors
- **Camera-equipped sensor nodes** — automated periodic crop imaging without farmer intervention
- **Agricultural expert feedback loop** — agronomists review and correct AI diagnoses to improve model accuracy over time

### Infrastructure Scaling

```mermaid
flowchart LR
    subgraph SF["🏡 Single Farm"]
        SF1["1 ESP32 Node"]
        SF2["1 Edge AI Gateway"]
        SF3["1 Farmer"]
    end

    subgraph VL["🏘️ Village"]
        VL1["Multiple ESP32 nodes per farm"]
        VL2["Village-level Edge AI Gateway"]
        VL3["Shared among multiple farmers"]
    end

    subgraph DT["🏙️ District"]
        DT1["Mesh network of village gateways"]
        DT2["District dashboard"]
        DT3["Aggregated insights"]
        DT4["Regional crop health maps"]
    end

    SF -->|Scale up| VL
    VL -->|Scale up| DT

    style SF fill:#E8F5E9,stroke:#2E7D32
    style VL fill:#E3F2FD,stroke:#1565C0
    style DT fill:#FFF3E0,stroke:#E65100
```

- **LoRa / mesh-based deployment** — extend sensor range beyond Wi-Fi using LoRa for farms without local network infrastructure
- **Village-level Edge AI Gateways** — a single gateway serving multiple farms, reducing per-farmer hardware cost
- **Offline synchronization** — queue recommendations locally during outages, sync when connectivity resumes
- **Federated / privacy-aware learning** — improve model performance using distributed farm data without centralizing sensitive information
- **Predictive crop-risk models** — use historical sensor + diagnosis data to predict disease outbreaks before symptoms appear
- **Larger regional deployments** — aggregate village-level data for district/state-level agricultural insights and policy support

---

## 19. 📚 Open-Source Dependencies / Components

| Component | Purpose | License / Source | Usage in AgriChain |
|:----------|:--------|:----------------|:-------------------|
| **Google Gemma 4** | Multimodal Edge AI model | [Gemma Terms of Use](https://ai.google.dev/gemma/terms) — Google | Core reasoning engine for crop diagnosis and recommendations |
| **PyTorch** | Deep learning framework | [BSD-3-Clause](https://github.com/pytorch/pytorch) | Model loading and inference runtime |
| **Transformers** | Model interface library | [Apache-2.0](https://github.com/huggingface/transformers) | Gemma 4 model loading, tokenization, inference |
| **FastAPI** | Web API framework | [MIT](https://github.com/tiangolo/fastapi) | Backend REST API |
| **SQLAlchemy** | Python ORM | [MIT](https://github.com/sqlalchemy/sqlalchemy) | Database access layer |
| **Pydantic** | Data validation | [MIT](https://github.com/pydantic/pydantic) | Request/response models, structured output parsing |
| **React Native** | Mobile framework | [MIT](https://github.com/facebook/react-native) | Cross-platform farmer mobile application |
| **React** | UI library | [MIT](https://github.com/facebook/react) | Web dashboard |
| **PostgreSQL** | Relational database | [PostgreSQL License](https://www.postgresql.org/) | Persistent data storage |
| **Arduino / ESP-IDF** | ESP32 firmware SDK | [LGPL / Apache-2.0](https://github.com/espressif/arduino-esp32) | Sensor reading, relay control, communication |
| **OpenCV** | Image processing | [Apache-2.0](https://github.com/opencv/opencv) | Image preprocessing for inference |
| **Pillow** | Image handling | [MIT-like (HPND)](https://github.com/python-pillow/Pillow) | Image loading, resizing, format conversion |
| **Docker** | Containerization | [Apache-2.0](https://github.com/moby/moby) | Deployment packaging |

> **Note:** Verify all licenses and attribution requirements before production redistribution. License information listed here reflects the state at the time of writing and should be confirmed against each project's current license file.

---

## 20. ⚠️ Expected Challenges and Mitigation

| Challenge | Risk Level | Description | Mitigation Strategy |
|:----------|:-----------|:------------|:--------------------|
| **Edge inference latency** | Medium | Gemma 4 inference on edge hardware may introduce perceptible delays | Optimize inference pipeline, use quantized models where appropriate, implement progress indicators in UI |
| **Edge hardware constraints** | Medium | Edge AI Gateway requires sufficient compute (RAM, GPU/NPU) for Gemma 4 | Profile memory and compute requirements, select appropriate edge hardware, consider model distillation |
| **Poor / intermittent connectivity** | High | Rural areas often lack reliable internet | Edge-first architecture — Gemma 4 runs locally; sync data when connectivity resumes; cache weather/market data |
| **Sensor noise and drift** | Medium | Soil moisture, temp, humidity sensors can produce noisy or drifting readings | Implement moving-average smoothing, calibration routines, outlier detection, periodic recalibration |
| **False crop diagnosis** | High | Gemma 4 may misidentify diseases, especially for crops/conditions outside its training distribution | Always present diagnoses as advisory; encourage farmer verification; track confidence indicators; build expert feedback loop |
| **LLM hallucination** | High | Gemma 4 may generate plausible but incorrect agricultural information | Constrain outputs via structured prompting; validate against known agricultural rules; never present AI output as certified diagnosis |
| **Incorrect agricultural advice** | Critical | Wrong treatment recommendations could damage crops or harm the environment | All recommendations pass through Decision / Safety Engine; flag low-confidence results; include disclaimers; consult agricultural extension |
| **Power availability** | Medium | ESP32 nodes in rural fields may face inconsistent power supply | Low-power design, sleep modes, solar panel options, battery backup |
| **Sensor calibration** | Low–Medium | Sensors require initial calibration and periodic recalibration for accuracy | Provide calibration procedures, store calibration offsets, alert on suspected drift |
| **Model updates** | Low | Updating Gemma 4 or fine-tuned weights on edge gateways in the field | OTA update mechanism for edge gateway; version management; rollback capability |
| **Privacy** | Medium | Farmer crop images and field data are sensitive | Process on-device at edge; minimize cloud transmission; encrypt data in transit and at rest |
| **Scalability** | Medium | Moving from single-farm prototype to multi-village deployment introduces infrastructure complexity | Modular architecture; village-level gateway aggregation; containerized deployment |
| **AI controlling safety-critical hardware** | Critical | Gemma 4 must **never** directly control relays, pumps, or other actuators | **All actuator commands must pass through the deterministic Decision / Safety Engine.** AI output is advisory only. Threshold validation, rule checks, and safety overrides are mandatory before any physical action. |

<blockquote>
<strong>⚠️ Safety-Critical Design Rule</strong>
<br><br>
Gemma 4 should <strong>NOT</strong> directly control safety-critical hardware without deterministic validation. The Decision / Safety Engine enforces hard thresholds, operational limits, and safety constraints that cannot be overridden by AI-generated recommendations. A human override mechanism must always be available.
</blockquote>

---

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Node.js 18+
- PostgreSQL 14+
- Docker (optional, for containerized deployment)
- ESP32 development environment (Arduino IDE or PlatformIO)
- Edge AI Gateway hardware with sufficient compute for Gemma 4

### Installation

```bash
# Clone the repository
git clone <REPOSITORY_URL>
cd agrichain
```

#### Backend Setup

```bash
# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate        # Linux / macOS
# .venv\Scripts\activate         # Windows

# Install dependencies
pip install -r requirements.txt
```

#### Environment Configuration

```bash
# Copy example environment file
cp .env.example .env
```

Edit `.env` with your configuration:

```env
# Database
DATABASE_URL=postgresql://user:password@localhost:5432/agrichain

# Weather API
WEATHER_API_KEY=your_weather_api_key
WEATHER_API_URL=https://api.weatherapi.com/v1

# Market Data
MARKET_API_KEY=your_market_api_key

# Edge AI Gateway
EDGE_GATEWAY_HOST=192.168.1.100
EDGE_GATEWAY_PORT=8081

# MQTT (ESP32 Communication)
MQTT_BROKER_HOST=localhost
MQTT_BROKER_PORT=1883

# Application
SECRET_KEY=your_secret_key
DEBUG=false
```

> **Security:** Never commit `.env` files or hard-code API keys. Use `.env.example` as a template with placeholder values only.

#### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

#### ESP32 Firmware

Flash the firmware from `firmware/` using Arduino IDE or PlatformIO. Update Wi-Fi credentials and MQTT broker address in the firmware configuration before flashing.

#### Run Backend

```bash
cd backend
uvicorn main:app --host 0.0.0.0 --port 8000
```

---

## 📁 Project Structure

> **Note:** This is the suggested project structure. Some files/directories may not yet exist if implementation is in progress.

```text
agrichain/
├── frontend/                   # React Native mobile app + React web dashboard
│   ├── mobile/                 # React Native farmer application
│   │   ├── src/
│   │   │   ├── screens/        # CropClinic, Dashboard, Weather, Market, Irrigation
│   │   │   ├── components/     # Reusable UI components
│   │   │   ├── services/       # API client, MQTT, notifications
│   │   │   └── utils/
│   │   └── package.json
│   └── web/                    # React admin/monitoring dashboard
│       ├── src/
│       └── package.json
├── backend/                    # FastAPI backend server
│   ├── app/
│   │   ├── api/                # API route handlers
│   │   ├── models/             # SQLAlchemy ORM models
│   │   ├── schemas/            # Pydantic request/response schemas
│   │   ├── services/           # Business logic, external API clients
│   │   ├── decision_engine/    # Deterministic safety/threshold engine
│   │   └── config.py
│   ├── main.py
│   └── requirements.txt
├── edge-ai/                    # Gemma 4 inference pipeline
│   ├── inference/              # Model loading, prompt construction, output parsing
│   ├── prompts/                # Agricultural prompt templates
│   ├── server.py               # Inference API server for Edge AI Gateway
│   └── requirements.txt
├── firmware/                   # ESP32 Arduino / PlatformIO firmware
│   ├── src/
│   │   ├── main.cpp            # Sensor reading, MQTT publishing, relay control
│   │   ├── sensors.h           # Sensor abstraction
│   │   └── config.h            # Wi-Fi, MQTT, pin configuration
│   └── platformio.ini
├── docs/                       # Additional documentation
│   ├── hardware-setup.md
│   ├── api-reference.md
│   └── deployment-guide.md
├── tests/                      # Test suites
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── docker-compose.yml          # Multi-service container orchestration
├── .env.example                # Environment variable template
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🔐 Security & Safety

| Concern | Approach |
|:--------|:---------|
| **API key protection** | All keys stored in `.env`, never committed to version control; `.env.example` provides templates with placeholder values |
| **Authentication** | JWT-based user authentication for mobile/web app; API key authentication for ESP32 ↔ backend |
| **Input validation** | Pydantic schema validation on all API inputs; image size/format checks before inference |
| **Secure device communication** | MQTT with TLS encryption for ESP32 ↔ backend; HTTPS for all API endpoints |
| **No hard-coded secrets** | All sensitive configuration loaded from environment variables |
| **Safe actuator control** | All relay/pump commands must originate from the Decision / Safety Engine after deterministic validation; maximum irrigation duration enforced; manual emergency stop |
| **Model output validation** | Structured output parsing with fallback handling; confidence thresholds; anomaly detection on AI recommendations |
| **Human override** | Farmer can manually override or cancel any automated irrigation action; all AI recommendations clearly marked as advisory |

---

## 🧪 Testing

| Test Category | Scope | Tools |
|:-------------|:------|:------|
| **Unit Testing** | Backend services, decision engine logic, structured output parsing | pytest, unittest |
| **API Testing** | FastAPI endpoint validation, request/response schemas, error handling | pytest + httpx, Postman |
| **Model / Inference Testing** | Gemma 4 prompt correctness, structured output format, edge case handling | Custom test harness, sample crop images |
| **Sensor Testing** | Sensor reading accuracy, calibration verification, noise characterization | Serial monitor, reference instruments |
| **Hardware Testing** | ESP32 ↔ relay ↔ pump operation, power management, Wi-Fi reconnection | Manual hardware validation, automated relay cycling |
| **End-to-End Testing** | Full flow: image capture → diagnosis → irrigation recommendation → pump activation | Integration test suite |
| **Offline Testing** | Edge AI Gateway operation without internet, data queuing, sync on reconnection | Network simulation, disconnect testing |

```bash
# Run backend tests
cd backend
pytest tests/ -v

# Run frontend tests
cd frontend
npm test
```

---

## 📸 Screenshots & Demo

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/dashboard.png" width="900" alt="AgriChain Farmer Dashboard"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/crop-clinic.png" width="900" alt="Crop Clinic — Disease Diagnosis"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/gemma4-inference.png" width="900" alt="Gemma 4 Edge AI Inference"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/disease-diagnosis.png" width="900" alt="Disease Diagnosis Result"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/iot-dashboard.png" width="900" alt="IoT Sensor Dashboard"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/smart-irrigation.png" width="900" alt="Smart Irrigation Assistant"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/esp32-hardware.png" width="900" alt="ESP32 Sensor Node Hardware"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/weather-module.png" width="900" alt="Weather Intelligence Module"/>
</p>

---

<p align="center">
  <img src="https://res.cloudinary.com/CLOUD_NAME/image/upload/v1/agrichain/market-insights.png" width="900" alt="Market Insights"/>
</p>

---

## 🎥 Demo

| Demo | Description | Link |
|:-----|:------------|:-----|
| **Full System Demo** | End-to-end walkthrough: farmer uploads image → Gemma 4 diagnosis → irrigation recommendation → pump activation | [Watch Demo](#) |
| **Architecture Walkthrough** | Technical explanation of system architecture, data flow, and Edge AI integration | [Watch Video](#) |
| **Gemma 4 Inference Demo** | Focused demonstration of Gemma 4 processing a crop image with sensor context and generating structured diagnosis | [Watch Demo](#) |
| **Hardware Demo** | ESP32 sensor node in operation — live sensor readings, relay activation, pump control | [Watch Demo](#) |

---

## 👥 Team

<h3 align="center">3Musketeers</h3>

<table align="center">
<tr>
<td align="center">
<strong>Ojas Dhapse</strong>
</td>
<td align="center">
<strong>Hansuja Jambhale</strong>
</td>
<td align="center">
<strong>Jheel Pashine</strong>
</td>
</tr>
</table>

---

## ⭐ Why AgriChain?

<blockquote>
<h3>AgriChain moves agricultural intelligence closer to the field.</h3>
</blockquote>

Most agricultural technology solutions assume reliable cloud connectivity, access to experts, and literate, tech-savvy users. AgriChain is designed for the reality of rural farming — where internet is intermittent, experts are distant, and decisions must be made at the field's edge.

By combining **Google Gemma 4** multimodal Edge AI with **ESP32 IoT sensing** and a **deterministic Decision / Safety Engine**, AgriChain transforms:

| **Raw Input** | **Into** |
|:-------------|:---------|
| A blurry photo of a wilting leaf | A structured disease diagnosis with severity and treatment steps |
| A soil moisture reading of 23% | A context-aware irrigation recommendation validated for safety |
| A farmer's voice question in the field | An actionable, farmer-friendly explanation |
| Scattered weather, market, and sensor data | A unified, coherent agricultural advisory |

**The combination:** Gemma 4 + Edge AI + IoT + Smart Irrigation + Deterministic Safety — working together to turn raw field data and farmer observations into **understandable, actionable, and safe decisions.**

AgriChain does not claim to replace agricultural experts. It aims to bring a meaningful level of agricultural intelligence to every field — even when the nearest expert is hours away and the nearest cell tower barely works.

---

<p align="center">
  <strong>Built with 🌱 for farmers, powered by <a href="https://ai.google.dev/gemma">Google Gemma 4</a></strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Google-Gemma_4-4285F4?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
  <img src="https://img.shields.io/badge/Edge_AI-Multimodal-FF6F00?style=flat-square" alt="Edge AI"/>
  <img src="https://img.shields.io/badge/ESP32-IoT-E7352C?style=flat-square&logo=espressif&logoColor=white" alt="ESP32"/>
  <img src="https://img.shields.io/badge/Smart-Irrigation-2196F3?style=flat-square" alt="Smart Irrigation"/>
</p>
