# Systems Analysis & Design (SAD) — Lecture 1
**Faculty:** Faculty of Computer and Information Sciences, Ain Shams University (FCIS ASU)

---

## Table of Contents

1. [SDLC](#1-systems-development-life-cycle-sdlc)
2. [Feasibility Study](#2-feasibility-study--analysis)
3. [Business Analyst vs. System Analyst](#3-business-analysis-vs-system-analysis)
4. [BACCM](#4-business-analysis-core-concept-model-baccm)
5. [CASE Tools & Software Sources](#5-case-tools--software-sources)
6. [Quick Memory Cheat Sheet](#6-quick-memory-cheat-sheet)

---

## Visual Concept Map (Lecture Overview)

```mermaid
mindmap
  root((SAD Lecture 1))
    1 SDLC
      6 phases
      Maintenance loops back
    2 Feasibility Study
      8 steps
      4 dimensions
    3 BA vs SA
      Business focus
      Technical focus
    4 BACCM
      6 core concepts
    5 Tools and Sources
      CASE tools
      Software sources
```

---

## 1. Systems Development Life Cycle (SDLC)

> **Definition:** The traditional, orderly methodology used to develop, maintain, and replace information systems. It yields working software, system documentation, and user training.

```mermaid
flowchart TD
    classDef phase fill:#2563eb,stroke:#fff,stroke-width:2px,color:#fff;

    P["1. Planning<br/>Why build? How to plan?<br/>Project initiation and management"]:::phase
    A["2. Analysis<br/>Who, What, Where, When?<br/>Requirements determination and structuring"]:::phase
    D["3. Design<br/>System specifications<br/>Logical (tech-independent) and Physical (tech-specific)"]:::phase
    I["4. Implementation<br/>Code, validate, install, support"]:::phase
    T["5. Testing<br/>Evaluate and correct errors"]:::phase
    M["6. Maintenance<br/>Systematic repair and improvement"]:::phase

    P --> A --> D --> I --> T --> M
    M -.->|Iterates back to| P
```

*Note: Maintenance is not a separate linear phase. It is a repetition of the other life cycle phases.*

| Phase | Key question / activity |
|---|---|
| Planning | Why build the system? How should the team plan it? |
| Analysis | Who uses it, what does it do, where and when is it used? |
| Design | Logical design (technology-independent) then Physical design (technology-specific) |
| Implementation | Code, validate, install, support |
| Testing | Evaluate and correct errors |
| Maintenance | Repair and improve, by repeating the earlier phases |

---

## 2. Feasibility Study & Analysis

> **Purpose:** A preliminary investigation that helps management decide whether development is viable. It gathers the problem outline and scope (**not** the solution) and outputs a formal **system proposal**.

### The 8 Steps of Feasibility Analysis

```mermaid
flowchart LR
    classDef step fill:#d97706,stroke:#fff,stroke-width:2px,color:#fff;

    S1("1. Form<br/>team"):::step --> S2("2. Develop<br/>flowcharts"):::step
    S2 --> S3("3. Identify<br/>deficiencies<br/>and goals"):::step
    S3 --> S4("4. Enumerate<br/>alternative<br/>solutions"):::step
    S4 --> S5("5. Determine<br/>feasibility<br/>of each"):::step
    S5 --> S6("6. Weigh<br/>cost and<br/>performance"):::step
    S6 --> S7("7. Rank and<br/>select best"):::step
    S7 --> S8("8. Prepare<br/>system<br/>proposal"):::step
```

**Grouping trick:** the 8 steps fall into three blocks:
- **Understand** (steps 1-3): team, flowcharts, deficiencies and goals
- **Explore** (steps 4-5): alternatives, feasibility of each
- **Decide** (steps 6-8): weigh, rank, write the proposal

### The 4 Core Feasibility Dimensions

```mermaid
graph TD
    classDef dim fill:#059669,stroke:#fff,stroke-width:2px,color:#fff;

    F[Feasibility Dimensions]:::dim --> E["Economic<br/>Estimates cost-effectiveness before funding"]:::dim
    F --> T["Technical<br/>Can existing tech support it, or are upgrades needed?"]:::dim
    F --> O["Operational<br/>User impact and acceptance of new methods"]:::dim
    F --> S["Schedule<br/>Are deadlines reasonable and achievable?"]:::dim
```

---

## 3. Business Analysis vs. System Analysis

> **Core skill categories (System Analyst):** Technical, business, analytical, interpersonal, management, and ethical.

```mermaid
graph LR
    classDef ba fill:#7c3aed,stroke:#fff,stroke-width:2px,color:#fff;
    classDef sa fill:#be185d,stroke:#fff,stroke-width:2px,color:#fff;

    BA["Business Analyst (BA)<br/>Discovers and synthesizes enterprise needs"]:::ba
    SA["System Analyst (SA)<br/>Applies technology to solve business problems"]:::sa

    BA -->|Primary focus| F1["Business processes, operational problems, strategic goals"]
    SA -->|Primary focus| F2["Technical execution, software aspects, architectures"]

    BA -->|Scope of work| S1["May work on improvements WITHOUT software changes"]
    SA -->|Scope of work| S2["ONLY involved when there is a software change"]
```

| | Business Analyst | System Analyst |
|---|---|---|
| Role | Discovers and synthesizes enterprise needs | Applies technology to solve business problems |
| Focus | Business processes, operational problems, strategic goals | Technical execution, software, architectures |
| Scope | Can improve things without any software change | Only involved when software changes |

---

## 4. Business Analysis Core Concept Model (BACCM)

Six core concepts. Read them as one sentence: a **Change** is triggered by a **Need**, satisfied by a **Solution**, for **Stakeholders**, creating **Value**, within a **Context**.

```mermaid
graph TD
    classDef core fill:#0f766e,stroke:#fff,stroke-width:2px,color:#fff;

    C(("CHANGE<br/>Act of transformation<br/>to improve performance")):::core

    N["NEED<br/>Problem or opportunity<br/>motivating action"]:::core
    S["SOLUTION<br/>Specific way of satisfying<br/>needs in a context"]:::core
    ST["STAKEHOLDER<br/>People with a stake<br/>in the change"]:::core
    V["VALUE<br/>Worth or importance<br/>(tangible or intangible)"]:::core
    CX["CONTEXT<br/>Circumstances influencing<br/>the change"]:::core

    C --- N
    C --- S
    C --- ST
    C --- V
    C --- CX
```

**Key details**
- **Stakeholders include:** customers, end users, project managers, regulators, suppliers, sponsors, testers.
- **Value:** *Tangible* (monetary, measurable) or *Intangible* (morale, reputation).
- **Context:** circumstances that influence the change (culture, demographics, technology, weather).

---

## 5. CASE Tools & Software Sources

### CASE Tools (Computer-Aided Software Engineering)

> Software that supports SDLC activities. It uses an integrated database called the **Central Repository** for specifications, diagrams, reports, and project information (e.g., Oracle Designer, Rational Rose).

```mermaid
graph TD
    classDef case fill:#0369a1,stroke:#fff,stroke-width:2px,color:#fff;

    CT[CASE Tool Types]:::case --> D1["Diagramming<br/>Process and data structures"]
    CT --> D2["Display / Report Generators<br/>Prototyping the UI"]
    CT --> D3["Analysis Tools<br/>Check specs for errors"]
    CT --> D4["Central Repository<br/>Integrated DB storage"]
    CT --> D5["Documentation Generators<br/>Technical and user manuals"]
    CT --> D6["Code Generators<br/>Auto-generate code from design"]
```

### Sources of Application Software

```mermaid
graph LR
    classDef src fill:#b45309,stroke:#fff,stroke-width:2px,color:#fff;

    SRC[Software Sources]:::src --> P["Packaged / COTS<br/>Microsoft, Oracle"]
    SRC --> C["Cloud Computing<br/>Google Apps, Salesforce"]
    SRC --> O["Open Source<br/>Linux, MySQL, Firefox"]
    SRC --> E["ERP Providers<br/>Shared DBs for HR / Accounting"]
    SRC --> I["In-House Development<br/>Custom built by internal IT"]
    SRC --> OUT["Outsourcing<br/>3rd-party firm to cut cost and time"]
```

| Source | Example | One-line idea |
|---|---|---|
| Packaged / COTS | Microsoft, Oracle | Buy ready-made software |
| Cloud | Google Apps, Salesforce | Rent it online |
| Open source | Linux, MySQL, Firefox | Free, community-built code |
| ERP | HR / Accounting systems | One shared DB across the company |
| In-house | Built by internal IT | Custom, full control |
| Outsourcing | 3rd-party firm | Hire someone else to build it |

---

## 6. Quick Memory Cheat Sheet

| Topic | Remember this |
|---|---|
| SDLC (6 phases) | **P**lanning → **A**nalysis → **D**esign → **I**mplementation → **T**esting → **M**aintenance ("PADITM"), and Maintenance loops back |
| Design types | Logical = tech-independent, Physical = tech-specific |
| Feasibility output | A formal **system proposal** (problem scope, not the solution) |
| Feasibility steps | Understand (1-3) → Explore (4-5) → Decide (6-8) |
| 4 dimensions | **E**conomic, **T**echnical, **O**perational, **S**chedule ("ETOS") |
| BA vs SA | BA = business needs, may change no software. SA = technology, only with software change |
| SA skills | Technical, business, analytical, interpersonal, management, ethical |
| BACCM | Change, Need, Solution, Stakeholder, Value, Context |
| CASE tools | Diagramming, Display/Report, Analysis, Central Repository, Documentation, Code generators |
| Software sources | Packaged, Cloud, Open source, ERP, In-house, Outsourcing |
