# Systems Analysis & Design (SAD) — Lecture 1
**Faculty:** Faculty of Computer and Information Sciences, Ain Shams University (FCIS ASU)  

---

## Visual Concept Map (Lecture Overview)

```mermaid
graph TD
    classDef primary fill:#4f46e5,stroke:#fff,stroke-width:2px,color:#fff;
    classDef secondary fill:#0284c7,stroke:#fff,stroke-width:2px,color:#fff;
    classDef tertiary fill:#0d9488,stroke:#fff,stroke-width:2px,color:#fff;

    Root[SAD Lecture 1: Core Concepts] --> SDLC[1. SDLC Phases]:::primary
    Root --> Feas[2. Feasibility Study]:::secondary
    Root --> BA_SA[3. Business vs System Analyst]:::tertiary
    Root --> BACCM[4. BACCM Model]:::primary
    Root --> Tools[5. CASE & Software Sources]:::secondary
    class Root primary;
```

---

## 1. 🔵 Systems Development Life Cycle (SDLC)

> **Definition:** The traditional, orderly methodology to develop, maintain, and replace information systems. Yields working software, system documentation, and user training.

```mermaid
flowchart TD
    classDef phase fill:#2563eb,stroke:#fff,stroke-width:2px,color:#fff;
    
    P["📋 1. Planning <br/>(Why build? How to plan?)<br/>Project Initiation & Mgmt"]:::phase --> A["🔍 2. Analysis <br/>(Who, What, Where, When?)<br/>Requirements Determination & Structuring"]:::phase
    A --> D["📐 3. Design <br/>(System Specs)<br/>Logical (Tech-independent) & Physical (Tech-specific)"]:::phase
    D --> I["💻 4. Implementation <br/>Code, Validate, Install, Support"]:::phase
    I --> T["🧪 5. Testing <br/>Evaluate & Correct Errors"]:::phase
    T --> M["🛠️ 6. Maintenance <br/>Systematic Repair & Improvement"]:::phase
    M -.->|Iterates back to| P
```
*(Note: Maintenance is not a separate linear phase, but a repetition of the other life cycle phases).*

---

## 2. 🟡 Feasibility Study & Analysis

> **Purpose:** A preliminary investigation to help management decide if development is viable. Acquires problem outline/scope (not the solution) to output a formal system proposal.

### 🧭 The 8 Steps of Feasibility Analysis
```mermaid
flowchart LR
    classDef step fill:#d97706,stroke:#fff,stroke-width:2px,color:#fff;
    
    S1("1. Form<br/>Team"):::step --> S2("2. Develop<br/>Flowcharts"):::step
    S2 --> S3("3. Identify<br/>Deficiencies<br/>& Goals"):::step
    S3 --> S4("4. Enumerate<br/>Alternative<br/>Solutions"):::step
    S4 --> S5("5. Determine<br/>Feasibility<br/>(Each)"):::step
    S5 --> S6("6. Weight<br/>Cost & Perf."):::step
    S6 --> S7("7. Rank &<br/>Select Best"):::step
    S7 --> S8("8. Prepare<br/>System Proposal"):::step
```

### 🎯 The 4 Core Feasibility Dimensions
```mermaid
graph TD
    classDef dim fill:#059669,stroke:#fff,stroke-width:2px,color:#fff;
    
    F[Feasibility Dimensions] --> E["💰 Economic<br/>Estimates cost-effectiveness<br/>before funding"]:::dim
    F --> T["⚙️ Technical<br/>Checks if existing tech<br/>supports it or needs upgrades"]:::dim
    F --> O["👥 Operational<br/>Analyzes user impact<br/>& acceptance of new methods"]:::dim
    F --> S["⏳ Schedule<br/>Ensures deadlines are<br/>reasonable & met"]:::dim
```

---

## 3. 💼 Business Analysis vs. System Analysis

> **Core Skill Categories (SA):** Technical, business, analytical, interpersonal, management, and ethical.

```mermaid
graph LR
    classDef ba fill:#7c3aed,stroke:#fff,stroke-width:2px,color:#fff;
    classDef sa fill:#be185d,stroke:#fff,stroke-width:2px,color:#fff;

    BA["🧑‍💼 Business Analyst (BA)<br/>Discovers & synthesizes enterprise needs"]:::ba
    SA["🧑‍💻 System Analyst (SA)<br/>Applies tech to solve business problems"]:::sa

    BA ---|Primary Focus| F1["Business processes,<br/>operational problems, strategic goals"]
    SA ---|Primary Focus| F2["Technical execution,<br/>software aspects, architectures"]

    BA ---|Scope of Work| S1["May work on improvements<br/>WITHOUT software changes"]
    SA ---|Scope of Work| S2["ONLY involved when there is<br/>a software change"]
```

---

## 4. 🎯 Business Analysis Core Concept Model (BACCM)

```mermaid
graph TD
    classDef core fill:#0f766e,stroke:#fff,stroke-width:2px,color:#fff;
    
    C(("🔄 CHANGES<br/>Act of transformation<br/>to improve performance")):::core
    
    N["🎯 NEEDS<br/>Problem/Opportunity<br/>motivating action"]:::core
    S["💡 SOLUTIONS<br/>Specific way of satisfying<br/>needs in context"]:::core
    V["💎 VALUE<br/>Worth/Importance<br/>(Tangible or Intangible)"]:::core
    
    ST["🧑‍🤝‍🧑 STAKEHOLDERS<br/>&<br/>🌐 CONTEXT (Environment)"]:::core

    C --> N
    C --> S
    C --> V
    N --> ST
    S --> ST
    V --> ST
```
**Key Details:**
*   **Stakeholders include:** Customers, end users, project managers, regulators, suppliers, sponsors, testers.
*   **Value:** Can be *Tangible* (monetary, measurable) or *Intangible* (morale, reputation).
*   **Context:** Circumstances influencing the change (culture, demographics, tech, weather).

---

## 5. 🛠️ CASE Tools & Software Sources

### 🧰 CASE Tools (Computer-Aided Software Engineering)
> Software supporting SDLC activities. Uses an integrated database called a **Central Repository** for specs, diagrams, reports, and project info (e.g., Oracle Designer, Rational Rose).

```mermaid
graph TD
    classDef case fill:#0369a1,stroke:#fff,stroke-width:2px,color:#fff;
    
    CT[CASE Tools Types]:::case --> D1["📊 Diagramming<br/>(Process/Data structures)"]
    CT --> D2["🖥️ Display/Report Generators<br/>(Prototyping UI)"]
    CT --> D3["🔍 Analysis Tools<br/>(Check specs for errors)"]
    CT --> D4["🗄️ Central Repository<br/>(Integrated DB storage)"]
    CT --> D5["📄 Documentation Generators<br/>(Tech/User manuals)"]
    CT --> D6["💻 Code Generators<br/>(Auto-generate code from design)"]
```

### 💿 Sources of Application Software
```mermaid
graph LR
    classDef src fill:#b45309,stroke:#fff,stroke-width:2px,color:#fff;
    
    SRC[Software Sources]:::src --> P["📦 Packaged / COTS<br/>(Microsoft, Oracle)"]
    SRC --> C["☁️ Cloud Computing<br/>(Google Apps, Salesforce)"]
    SRC --> O["🔓 Open Source<br/>(Linux, MySQL, Firefox)"]
    SRC --> E["🏢 ERP Providers<br/>(Shared DBs for HR/Accounting)"]
    SRC --> I["🏗️ In-House Development<br/>(Custom built by internal IT)"]
    SRC --> OUT["🤝 Outsourcing<br/>(3rd party firm to cut costs & time)"]
```
