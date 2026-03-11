## Purpose

This document defines the structure, rules, and intended use of the lab’s Obsidian research vault.

The vault is designed to function as a **long-term research knowledge system**, not simply a literature note repository.

Primary goals:

- accumulate literature knowledge across projects and researchers
    
- support both **method development** and **clinical insight discovery**
    
- enable **fast manuscript writing** from reusable notes
    
- capture both **conceptual insights** and **quantitative evidence**
    
- scale across **hundreds of papers and many gait metrics**
    

The system separates **sources, insights, and numerical evidence** so knowledge remains reusable across projects.

---

# Core Design Principles

1. **One vault, not multiple vaults**
    
    Method papers, clinical papers, and project ideas belong in the same system.
    
2. **Organize knowledge, not manuscripts**
    
3. **Paper notes provide context, not summaries**
    
4. **Insight notes capture reusable scientific claims**
    
5. **Reference data notes capture numerical evidence**
    
6. **Ontology nodes define shared vocabulary**
    
7. **Use links aggressively**
    
8. **Extract minimally from papers**
    

Typical output from one paper:

1–5 insight notes  
0–2 reference data notes

---

# Relationship Between Zotero and Obsidian

Zotero and Obsidian serve different roles.

## Zotero

Zotero is the **bibliographic database** and should store:

- authors
    
- journal
    
- publication year
    
- DOI
    
- abstract
    
- keywords
    
- PDFs
    
- citation metadata
    

These should **not be duplicated inside Obsidian properties**.

---

## Obsidian

Obsidian stores:

- conceptual knowledge
    
- insights extracted from literature
    
- relationships between concepts
    
- numerical reference values
    

Obsidian functions as a **knowledge graph built on top of the literature database**.

---

# Top-Level Folder Structure

00_Inbox/  
01_Papers/  
02_Insights/  
03_Ontology/  
    populations/  
    activities/  
    methods/  
    metrics/  
    metric_domains/  
    properties/  
04_Reference_Data/  
05_Projects/  
06_Manuscripts/  
_templates/

---

# Folder Roles

## 00_Inbox

Temporary location for incomplete or unprocessed notes.

---

## 01_Papers

One note per literature source.

Paper notes serve as **navigation hubs linking insights and extracted data**.

---

## 02_Insights

Atomic scientific claims extracted from literature.

Insight notes are the **primary reusable knowledge unit**.

---

## 03_Ontology

Controlled vocabulary used across the vault.

These notes define concepts such as:

- populations
    
- activities
    
- methods
    
- metrics
    
- metric domains
    
- properties
    

---

## 04_Reference_Data

Structured numerical results extracted from papers.

These support insights with **quantitative evidence**.

---

## 05_Projects

Notes linking literature knowledge to active research projects.

---

## 06_Manuscripts

Working notes used when assembling papers or reports.

---

## _templates

Templates used when creating standardized notes.

---

# Knowledge Model

Knowledge in the vault is structured around the conceptual relationship:

Population × Activity × Metric × Property × Method

Example:

Multiple Sclerosis  
× Turning  
× Turn Duration  
× Reliability  
× Instrumented Insoles

This framework allows flexible connections between studies and findings.

---

# Ontology Structure

Ontology nodes define the conceptual vocabulary used across the vault.

## Populations

Examples:

- Multiple Sclerosis
    
- Parkinson’s Disease
    
- Healthy Adults
    
- CIDP
    

---

## Activities

Examples:

- Straight-line Walking
    
- Turning
    
- Stairs Up
    
- Stairs Down
    
- Free-living Walking
    

---

## Methods

Examples:

- Instrumented Insoles
    
- IMU
    
- Motion Capture
    
- Force Plates
    
- Activity Recognition
    

---

# Metric Domains

Metric domains organize gait metrics into clinically meaningful categories.

The vault adopts the widely used gait framework consisting of the following domains:

- **Pace**
    
- **Rhythm**
    
- **Variability**
    
- **Asymmetry**
    
- **Postural Control**
    

Folder structure:

03_Ontology/  
    metric_domains/  
        Pace  
        Rhythm  
        Variability  
        Asymmetry  
        Postural Control

Example relationships:

Stride Time → Rhythm  
Stride Length → Pace  
Stride Velocity → Pace  
Stride Time Variability → Variability  
Stride Time Asymmetry → Asymmetry  
Double Support Time → Postural Control

Domains provide a conceptual grouping of metrics and allow queries such as:

- all variability findings in MS
    
- all pace-related metrics studied in Parkinson’s disease
    

---

# Metrics

Examples:

- Stride Time
    
- Stride Length
    
- Stride Velocity
    
- Cadence
    
- Double Support Time
    

Metrics should link to their domain.

Example metric note:

# Stride Time  
  
Domain: [[Rhythm]]

---

# Properties

Properties describe the **type of relationship being studied**.

Examples:

- Reliability
    
- Validation
    
- Variability
    
- Sensitivity
    
- Detection
    
- Clinical Association
    

---

# Use of Properties (Frontmatter)

Properties should be used **sparingly and intentionally**.

The purpose of properties is to enable **knowledge queries**, not to recreate Zotero metadata.

---

# Paper Note Properties

Paper notes require only minimal metadata.

Example:

---  
type: paper  
citekey: smithValidationInsoles2024  
year: 2024  
---

Optional:

status: unread / reading / processed

All conceptual information should appear **inside the note body as links**.

Example:

Population:  
[[Multiple Sclerosis]]  
  
Activity:  
[[Straight-line Walking]]  
  
Method:  
[[Instrumented Insoles]]

This prevents duplication with Zotero.

---

# Insight Note Properties

Insight notes represent relationships between concepts and therefore benefit from structured properties.

Recommended structure:

---  
type: insight  
population:  
activity:  
metric:  
domain:  
property:  
method:  
source:  
citekey:  
---

These properties allow insights to be queried using:

- Obsidian Bases
    
- Dataview
    
- graph exploration
    

---

# Paper Notes (01_Papers)

Paper notes act as **navigation hubs**, not full summaries.

Example structure:

---  
type: paper  
citekey: smithValidationInsoles2024  
year: 2024  
---  
  
# Smith et al. — Validation of Instrumented Insoles  
  
## Study Context  
  
Population:  
- [[Healthy Adults]]  
- [[Multiple Sclerosis]]  
- [[Parkinson's Disease]]  
  
Activity:  
- [[Straight-line Walking]]  
  
Methods:  
- [[Instrumented Insoles]]  
- [[Motion Capture]]  
  
Sample Size:  
Healthy: 20  
PwMS: 18  
PwPD: 15  
  
---  
  
## Metrics Studied  
  
- [[Stride Time]]  
- [[Stance Time]]  
- [[Swing Time]]  
- [[Stride Length]]  
- [[Cadence]]  
- [[Stride Velocity]]  
  
---  
  
## Key Insights Extracted  
  
- [[Instrumented insoles show small bias relative to motion capture]]  
- [[Stride velocity differs between MS and healthy adults]]  
  
---  
  
## Reference Data Extracted  
  
- [[smithValidationStudy2024 — Agreement Metrics]]  
- [[smithValidationStudy2024 — Group Differences]]  
  
---  
  
## Notes (Optional)  
  
Observations that may later become insights.

Paper notes should generally remain **short (100–200 words)**.

---

# Insight Notes (02_Insights)

Insight notes capture **one reusable scientific claim**.

Example structure:

---  
type: insight  
population:  
activity:  
metric:  
domain:  
property:  
method:  
source:  
citekey:  
---  
  
Claim statement.  
  
Evidence:  
Brief explanation of the finding.  
  
Reference Data:  
Links to supporting numerical tables if applicable.

Example title:

Stride velocity decreases with EDSS in multiple sclerosis

Insight notes are designed to be **directly reusable in manuscripts**.

---

# Reference Data Notes (04_Reference_Data)

Reference data notes store **numerical results extracted from papers**.

These usually correspond to:

- one table
    
- one dataset
    
- one group of related numerical results
    

Example note:

smithValidationStudy2024 — Agreement Metrics

Tables from papers may be pasted directly with minimal formatting.

Example:

Source: [[smithValidationStudy2024]]  
Citation: @smithValidationStudy2024  
  
| Metric | Population | Mean | Bias | LoA Upper | LoA Lower |  
|------|------|------|------|------|------|  
| [[Stride Time]] | [[Healthy Adults]] | 1.151 | -0.016 | 0.021 | -0.053 |  
| [[Stride Time]] | [[Multiple Sclerosis]] | 1.375 | -0.019 | 0.034 | -0.072 |

Metric names should be **linked to ontology nodes**.

This enables retrieval via backlinks.

---

# Query Strategy

The system relies on **link-based querying** rather than rigid databases.

Example workflow:

Search: Stride Time  
↓  
Open Stride Time ontology page  
↓  
View backlinks  
↓  
See all insights and reference data mentioning this metric

This approach scales naturally as the vault grows.

---

# Minimal Workflow for Processing a Paper

1. Import paper into Zotero.
    
2. Create paper note in `01_Papers`.
    
3. Extract **1–5 insight notes**.
    
4. Extract **reference data notes if numerical values are important**.
    
5. Link insights and data to ontology nodes.
    

Typical processing time:

~5 minutes per paper

---

# Collaboration Rules

1. The vault is **shared research infrastructure**.
    
2. Prefer linking existing ontology nodes rather than creating new ones.
    
3. Insight notes should remain short and reusable.
    
4. Reference data notes should capture only **numbers likely to be cited later**.
    
5. Avoid long narrative summaries of papers.
    

---

# Conceptual Model of the Vault

Knowledge flows through three layers:

Paper → Insight → Reference Data

Paper notes provide context.

Insight notes capture reusable scientific claims.

Reference data notes capture supporting numerical evidence.

Ontology nodes provide the conceptual framework connecting everything.