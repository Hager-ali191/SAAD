# Systems Analysis & Design — Project Planning
**Faculty:** Faculty of Computer and Information Sciences, Ain Shams University (FCIS ASU)

---

## Table of Contents

1. [Planning Stages](#1-project-planning-stages--overview)
2. [Software Pricing](#2-software-pricing--factors)
3. [Plan-Driven Development](#3-plan-driven-development--project-plans)
4. [Iterative Planning Flow](#4-the-iterative-planning-process)
5. [Project Scheduling](#5-project-scheduling)
6. [Activity Network & Critical Path](#6-activity-network-diagram--critical-path)
7. [Time Estimation](#7-time-estimation--expected-time-formula)
8. [ASU Career Week](#8-ain-shams-university-career-week-asu-cw-25)
9. [Quick Memory Cheat Sheet](#9-quick-memory-cheat-sheet)

---

## Visual Concept Map (Lecture Overview)

```mermaid
mindmap
  root((Project Planning))
    1 Planning Stages
      Proposal
      Startup
      Development
    2 Software Pricing
      Strategies
      Price factors
    3 Plan-Driven Dev
      Pros and Cons
      Plan sections
    4 Iterative Flow
      Monitor and re-plan
    5 Scheduling
      5-step process
    6 Activity Network
      Critical Path
    7 Time Estimation
      O + 4M + P over 6
    8 ASU Career Week
```

---

## 1. Project Planning Stages & Overview

**Core purpose:** Break work into parts, assign team members, anticipate problems, and communicate how the work will be done to the team and the customer. The plan is created at project start and used to assess progress.

```mermaid
flowchart TD
    classDef stage fill:#2563eb,stroke:#fff,stroke-width:2px,color:#fff;

    P["1. Proposal Planning<br/>(Bidding phase, outline requirements)<br/>Goal: set the system price for the customer"]:::stage
    S["2. Project Startup Planning<br/>(Requirements known, design pending)<br/>Goal: allocate resources, budget, staffing"]:::stage
    D["3. Development Planning<br/>(Happens periodically during the project)<br/>Goal: keep amending schedule, costs, risks"]:::stage

    P --> S --> D
```

---

## 2. Software Pricing & Factors

**Overview:** Price starts from the cost of production (hardware, software, travel, training, effort), but organizational, economic, political and business considerations influence the final price charged.

### Pricing Strategies

```mermaid
graph LR
    classDef strat fill:#7c3aed,stroke:#fff,stroke-width:2px,color:#fff;

    PS[Pricing Strategies]:::strat --> UP["Under Pricing<br/>Win the contract to retain staff<br/>or enter a new market area"]:::strat
    PS --> IP["Increased Pricing<br/>Fixed-price contract buffer<br/>to cover unexpected risks"]:::strat
```

### Factors Affecting Software Price

```mermaid
graph TD
    classDef fact fill:#059669,stroke:#fff,stroke-width:2px,color:#fff;

    FP[Price Adjustments]:::fact --> CT["Contractual Terms<br/>Developer keeps code reuse rights = lower price"]:::fact
    FP --> EU["Cost Estimate Uncertainty<br/>Add contingency buffer on top of normal profit"]:::fact
    FP --> FH["Financial Health<br/>Lower price to improve cash flow in tough times"]:::fact
    FP --> MO["Market Opportunity<br/>Low initial profit to enter a future market segment"]:::fact
    FP --> RV["Requirements Volatility<br/>Low initial bid, high charges for later changes"]:::fact
```

---

## 3. Plan-Driven Development & Project Plans

**Definition:** The traditional approach to managing large projects, using a detailed plan that records the work, schedules, and work products.

### Pros and Cons

```mermaid
graph LR
    classDef pros fill:#047857,stroke:#fff,stroke-width:2px,color:#fff;
    classDef cons fill:#b91c1c,stroke:#fff,stroke-width:2px,color:#fff;

    PDD[Plan-Driven Development]
    PDD --- PROS["PROS<br/>- Early planning considers staff availability<br/>- Discovers dependencies before the project starts"]:::pros
    PDD --- CONS["CONS<br/>- Early decisions often must be revised<br/>as the environment changes"]:::cons
```

### Project Plan Sections & Supplements

```mermaid
graph TD
    classDef main fill:#2563eb,stroke:#fff,color:#fff;
    classDef sup fill:#9333ea,stroke:#fff,color:#fff;

    PP[Project Plan]:::main --> M[Main Sections]:::main
    PP --> SP[Supplementary Plans]:::sup

    M --> M1[Introduction]
    M --> M2[Project organization]
    M --> M3[Risk analysis]
    M --> M4[Resource requirements]
    M --> M5[Work breakdown]
    M --> M6[Schedule]
    M --> M7[Monitoring / reporting mechanisms]

    SP --> S1["Configuration Management Plan<br/>procedures and structures"]
    SP --> S2["Deployment Plan<br/>deployment and legacy data migration"]
    SP --> S3["Maintenance Plan<br/>predicts requirements, costs, effort"]
    SP --> S4["Quality Plan<br/>quality procedures and standards"]
    SP --> S5["Validation Plan<br/>approach, resources, schedule for validation"]
```

---

## 4. The Iterative Planning Process

**Concept:** Planning is iterative. Plans change because of requirements, schedules, risks, and shifting business goals. **Always include contingencies in your plans.**

```mermaid
flowchart TD
    classDef step fill:#d97706,stroke:#fff,stroke-width:2px,color:#fff;
    classDef bad fill:#b91c1c,stroke:#fff,stroke-width:2px,color:#fff;

    S1["1. Identify constraints, risks, milestones, deliverables"]:::step --> S2["2. Define project schedule"]:::step
    S2 --> S3["3. Do the work"]:::step
    S3 --> S4["4. Monitor progress against plan"]:::step

    S4 -->|No problems| S3
    S4 -->|Minor problems and slippages| S2
    S4 -->|Serious problems| S5["Initiate risk mitigation and re-plan project"]:::bad
    S5 --> S1
```

---

## 5. Project Scheduling

**Definition:** Deciding how work is organized into separate tasks, and estimating calendar time, effort, resources, and staffing.

### Scheduling Process

```mermaid
flowchart LR
    classDef sched fill:#0284c7,stroke:#fff,stroke-width:2px,color:#fff;

    IN[Requirements and Design]:::sched --> AC["1. Identify activities"]:::sched
    AC --> DEP["2. Identify dependencies"]:::sched
    DEP --> RES["3. Estimate resources"]:::sched
    RES <-->|Iterative loop| PEOP["4. Allocate people"]:::sched
    PEOP --> CH["5. Create project charts (bar charts)"]:::sched
```

**Scheduling problems:**
- Productivity is **not** proportional to the number of staff.
- Adding people to a late project makes it **later**, because of communication overheads.

---

## 6. Activity Network Diagram & Critical Path

**Definition:** A diagram showing sequential relationships between activities using arrows and nodes, used to find the **critical path**: the longest sequence of activities, which determines the expected completion time.

### House Building Example

| Activity | Task | Duration |
|---|---|---|
| A | Excavate | 5 d |
| B | Foundation | 2 d |
| C | Frame | 12 d |
| D | Electrical | 9 d |
| E | Roof | 5 d |
| F | Masonry | 8 d |
| G | Interior | 10 d |
| H | Exterior | 7 d |
| I | Landscape | 5 d |

```mermaid
graph LR
    classDef normal fill:#e0f2fe,stroke:#0369a1,stroke-width:2px,color:#0f172a;
    classDef critical fill:#fee2e2,stroke:#b91c1c,stroke-width:3px,color:#7f1d1d;

    Start((Start)):::critical --> A["A: Excavate (5d)"]:::critical
    A --> B["B: Foundation (2d)"]:::critical
    B --> C["C: Frame (12d)"]:::critical

    C --> D["D: Electrical (9d)"]:::critical
    C --> E["E: Roof (5d)"]:::normal
    C --> F["F: Masonry (8d)"]:::normal

    D --> G["G: Interior (10d)"]:::critical

    E --> H["H: Exterior (7d)"]:::critical
    F --> H
    G --> H

    H --> I["I: Landscape (5d)"]:::critical
    I --> End((End)):::critical

    %% Highlight the critical path links (0-3, 6, 9-11)
    linkStyle 0,1,2,3,6,9,10,11 stroke:#b91c1c,stroke-width:3px;
```

**Critical path:** START ➔ A ➔ B ➔ C ➔ D ➔ G ➔ H ➔ I ➔ END

**Total project duration:** 5 + 2 + 12 + 9 + 10 + 7 + 5 = **50 days**

Why not the other branches? After C, the three paths to H take:
- via D and G: 9 + 10 = **19 d** (longest, so critical)
- via F: 8 d
- via E: 5 d

**Critical rule:** Any delay to an activity on the critical path delays the entire project.

### Same project as a timeline (Gantt)

```mermaid
gantt
    title House Building Schedule (days from start)
    dateFormat  X
    axisFormat  Day %s

    section Critical path
    A Excavate       :crit, a, 0, 5
    B Foundation     :crit, b, after a, 2
    C Frame          :crit, c, after b, 12
    D Electrical     :crit, d, after c, 9
    G Interior       :crit, g, after d, 10
    H Exterior       :crit, h, after g, 7
    I Landscape      :crit, i, after h, 5

    section Non-critical (has slack)
    E Roof           :e, after c, 5
    F Masonry        :f, after c, 8
```

---

## 7. Time Estimation & Expected Time Formula

Each activity gets three estimates:

```mermaid
graph TD
    classDef time fill:#0d9488,stroke:#fff,stroke-width:2px,color:#fff;

    TE[Time Estimations]:::time --> O["Optimistic Time (O)<br/>Shortest possible time"]:::time
    TE --> M["Most Likely Time (M)<br/>Realistic expected completion time"]:::time
    TE --> P["Pessimistic Time (P)<br/>Longest, worst-case time"]:::time
```

**Expected Time formula:**

$$\text{Expected Time} = \frac{O + 4M + P}{6}$$

**Worked example:** O = 2 days, M = 5 days, P = 14 days

Expected = (2 + 4 × 5 + 14) / 6 = 36 / 6 = **6 days**

Note how the expected time (6) is pulled above the most likely time (5) by the pessimistic estimate. The "4×" weight shows that the most likely value counts the most.

---

## 8. Ain Shams University Career Week (ASU CW 25)

```mermaid
graph LR
    classDef event fill:#4f46e5,stroke:#fff,stroke-width:2px,color:#fff;

    EX["1. Attend Exhibition Days<br/>(Oct 19-23 at Career Center)"]:::event --> BO["2. Reserve a spot at the Career Center booth"]:::event
    BO --> RE["3. Attend Recruitment Days"]:::event
```

**Organized by:** Ain Shams University, Banque Misr.

---

## 9. Quick Memory Cheat Sheet

| Topic | Remember this |
|---|---|
| 3 planning stages | **P**roposal → **S**tartup → **D**evelopment ("PSD") |
| 2 pricing strategies | Under-pricing (win/retain) vs. Increased pricing (risk buffer) |
| 5 price factors | **C**ontract, **E**stimate uncertainty, **F**inancial health, **M**arket opportunity, **R**equirements volatility ("CEFMR") |
| Plan-driven | Pro: dependencies found early. Con: decisions need revising |
| 5 supplementary plans | Configuration, Deployment, Maintenance, Quality, Validation |
| Iterative loop | Plan → Work → Monitor → (OK / minor: re-schedule / serious: re-plan) |
| 5 scheduling steps | Activities → Dependencies → Resources → People → Charts |
| Brooks's law (here) | Adding people to a late project makes it later |
| Critical path | The **longest** path = project duration (50 days in the house example) |
| Expected time | (O + 4M + P) / 6 |

```mermaid
pie showData
    title House Project: Time on Critical Path (days)
    "A Excavate" : 5
    "B Foundation" : 2
    "C Frame" : 12
    "D Electrical" : 9
    "G Interior" : 10
    "H Exterior" : 7
    "I Landscape" : 5
```
