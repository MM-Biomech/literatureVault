> **Prerequisites:** This guide assumes you have completed `QUICKSTART.md` and have processed at least a handful of papers. The workflows below only become powerful once the vault contains a critical mass of insights (~20–50) and ontology nodes.

---

# Vault in Practice — Writing Papers and Planning Projects

This document shows what the vault is designed to *produce*: manuscript sections assembled from reusable notes, and research projects anchored in the literature you have already processed. It is intended to make the end goal concrete for new lab members.

---

## The Core Promise

When the vault is mature, you do not write a paper from scratch. You **assemble it from notes you already wrote while reading**.

Every insight note you created while processing a paper is a sentence that can go directly into a manuscript. Every reference data note is a table you can adapt. Every ontology node is a concept you can cite by name, knowing exactly which papers and insights back it up.

The vault turns reading into a reusable asset — not a memory.

---

# Part 1 — Writing a Paper

## The Big Picture

A manuscript has four main sections that map directly onto vault note types:

| Manuscript Section | Vault Source |
|---|---|
| Introduction | Insight notes filtered by population + property |
| Methods | Ontology method nodes + paper note Methods Details |
| Results | Reference data notes + your own study's data |
| Discussion | Insight notes filtered by domain + property; contested insights for counterarguments |

---

## Step-by-Step: Introduction and Discussion

### 1. Open the Insight Explorer

`00_Inbox/Insight Explorer.md`

This is a live query dashboard. Filter it by the variables relevant to your paper:

- **population** — e.g. `Parkinsons Disease`
- **domain** — e.g. `Variability`
- **property** — e.g. `Clinical Association`

The table returns every insight note matching those criteria, with the claim sentence as the note title.

### 2. Click through the insight notes

Each insight note has:
- A single **manuscript-ready claim sentence** as its title and body
- YAML fields that tell you population, metric, domain, property, and the source citekey
- Links to the paper note and any supporting reference data

The claim sentence is already written in scientific English. In many cases it goes straight into a paragraph with minor editing.

### 3. Use contested insights

If an insight is marked `contested: true`, it has a linked counter-insight. This gives you the "however, some evidence suggests…" sentence for free.

### 4. Check ontology nodes for coverage

Open any metric or population ontology node (e.g. `03_Ontology/metrics/Stride Velocity`).

The `## Referenced In` section at the bottom is a live query showing:
- Every paper that studied this metric
- Every insight extracted from those papers
- Every reference data table containing values for this metric

This tells you instantly how much literature exists on a topic and where the gaps are.

---

## Step-by-Step: Methods Section

### 1. Open the relevant method ontology nodes

Example: `03_Ontology/methods/IMU`, `03_Ontology/methods/ICC`

The `## Referenced In` section shows every paper in the vault that used this method. These are your citations.

### 2. Pull Methods Details from paper notes

Each paper note has a `## Study Context → Methods Details` section (auto-filled from Magenta highlights in Zotero). This contains the verbatim method descriptions from the source papers — useful as drafts or comparison material.

---

## Step-by-Step: Results Section

### 1. Use reference data notes as table templates

`04_Reference_Data/` contains structured numerical tables — one per research question. Each table already has the Metric and Population columns linked to ontology nodes, making it trivial to find comparable values from other papers.

To find all reference data relevant to your topic:
- Open the metric ontology node → `## Referenced In` → Reference Data section
- Or use Obsidian's backlinks panel on any metric node

### 2. Adapt, don't copy

Reference data notes are source material. Adapt the table structure to match your paper's reporting format (e.g. swap SD for LoA if you're running a Bland-Altman analysis).

---

## Step-by-Step: Building the Reference List

1. In the Insight Explorer, collect the `citekey` values of every insight you used
2. Open Zotero — every citekey maps directly to an item in the shared group library
3. Use the Zotero Word plugin to insert citations into your manuscript draft

You never need to manually look up a paper again. The citekey is the bridge.

---

## What a Mature Vault Looks Like During Manuscript Writing

```
Insight Explorer (filtered by population = "Parkinsons Disease", domain = "Variability")
│
├── Stride time variability is elevated in PD relative to healthy adults  → citekey: jones2022...
├── CoV of stride time correlates with fall history in PD                 → citekey: smith2021...
├── Variability increases during dual-task walking in PD                  → citekey: lee2023...
│
└── Reference Data:
    ├── jones2022 — Normative CoV Values by Group
    └── smith2021 — Stride Time Variability and Falls
```

Those four items give you the Introduction paragraph on gait variability in Parkinson's disease, two citations for the Results comparison section, and a table of normative values — all from notes you took while reading.

---

# Part 2 — Planning a Project

## The Big Picture

A project note in `05_Projects/` is a **live dashboard** that connects your research question to everything the vault already knows about it.

It does three things:
1. Defines the question with wikilinks to the relevant ontology nodes
2. Pulls a live table of all insights already in the vault matching the target population
3. Surfaces all papers already linked to this project

---

## Step-by-Step: Starting a New Project Note

### 1. Create the project note

Run **Templater: Create new note from template** → `project_note.md`

Name it after your project (e.g. `Insole Validation in MS — Turning Study`).

The note auto-moves to `05_Projects/`.

### 2. Fill the Research Question

Write one sentence. This is the north star for everything that follows.

Example:
> Do instrumented insoles reliably measure turning-related gait metrics in people with Multiple Sclerosis?

### 3. Link the ontology nodes

Fill in:
- **Populations** → `[[Multiple Sclerosis]]`
- **Key Metrics** → `[[Turn Duration]]`, `[[Stride Velocity]]`
- **Key Methods** → `[[Instrumented Insoles]]`, `[[ICC]]`

### 4. Let the live queries do the work

The `## Relevant Insights` Dataview query auto-populates with every insight note matching the population you specified. Edit the `WHERE` clause to refine by domain or property.

The `## Relevant Papers` query shows every paper note that has been linked back to this project (by adding a wikilink to the project note in the paper's `## Notes` section).

### 5. Identify gaps

Look at the Relevant Insights table. Ask:

- Which domains are well-covered? Which are missing?
- Do you have reliability data? Validation data? Clinical association data?
- Are there populations you want to compare against (e.g. `[[Healthy Adults]]`) that have little data?

The gaps in the table are your research gaps. They become your justification section.

### 6. Track open questions

Use the `## Open Questions` section to log unanswered questions as you read. These become the hypotheses for your study.

---

## What a Mature Project Note Looks Like

```
# Insole Validation in MS — Turning Study

## Research Question
Do instrumented insoles reliably measure turning-related gait metrics in people with Multiple Sclerosis?

## Populations
- [[Multiple Sclerosis]]
- [[Healthy Adults]]  (age-matched control)

## Key Metrics
- [[Turn Duration]]
- [[Turn Velocity]]
- [[Stride Velocity]]

## Key Methods
- [[Instrumented Insoles]]
- [[ICC]]
- [[Bland-Altman]]

---

## Relevant Insights  [LIVE TABLE — 12 results]
| Note | Population | Metric | Domain | Property | Source |
|------|------------|--------|--------|----------|--------|
| Stride velocity is reduced in MS... | Multiple Sclerosis | Stride Velocity | Pace | Clinical Association | jones2022 |
| ICC for stride time exceeds 0.90 in MS... | Multiple Sclerosis | Stride Time | Rhythm | Reliability | smith2021 |
| ... | ... | ... | ... | ... | ... |

---

## Relevant Papers  [LIVE TABLE — 8 results]
| Paper | Year | Status |
|-------|------|--------|
| jones2022GaitMS | 2022 | processed |
| ... | ... | ... |

---

## Open Questions
- Is ICC comparable between MS and healthy adults for turning metrics?
- What is the minimum number of turns needed for reliable estimates?
```

This note becomes the living literature review for your project. Every time a team member processes a new paper on a related topic and links it to the project, it appears in the Relevant Papers table automatically.

---

# Part 3 — The Feedback Loop

The vault is self-reinforcing. The more papers you process, the more powerful both workflows become.

```
Read a paper
    ↓
Create insight notes (02_Insights)
    ↓
Insights appear in Insight Explorer and project note live queries
    ↓
Link to project note from paper Notes section
    ↓
Paper appears in project note Relevant Papers table
    ↓
Write manuscript using insight sentences + reference data tables
    ↓
Insights that were used become the backbone of Introduction and Discussion
    ↓
New paper adds citations that feed back into the vault as new papers to process
```

A paper you processed six months ago for a different project contributes to the next manuscript automatically — because the insight was written to be reusable, not tied to a single context.

---

# Summary for New Lab Members

| You want to… | Go to… |
|---|---|
| Find what the lab knows about a gait metric | `03_Ontology/metrics/[Metric Name]` → Referenced In |
| Find all insights on a topic for manuscript writing | `00_Inbox/Insight Explorer.md` |
| See what papers still need processing | `00_Inbox/Processing Queue.md` |
| Start planning a new study | `05_Projects/` → create from `project_note.md` |
| Find numerical comparison values from the literature | `04_Reference_Data/` or metric ontology node → Referenced In |
| See every paper that used a specific method | `03_Ontology/methods/[Method Name]` → Referenced In |

The vault is a shared resource. Every paper you process and every insight you extract makes the system more useful for every other team member working on a related question.
