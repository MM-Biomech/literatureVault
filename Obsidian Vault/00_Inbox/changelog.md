# Vault Changelog

---

## 2026-03-17 — Processing Queue Expansion, Insight Template Fix, Reference Data in Referenced In

### Added

- `00_Inbox/Processing Queue.md` — two new sections:
  - **Missing Insight Files** — DataviewJS query using reverse ontology logic: unresolved wikilinks with 7+ words in paper notes = named insights without files; shows source paper for each
  - **Incomplete Insight Notes** — Dataview query flagging insight files in `02_Insights/` missing `citekey`, `population`, or `metric`; catches notes created by clicking a link but never filled in
- Processing Queue now covers the full pipeline in 5 stages: papers pending extraction → missing insight files → incomplete insight notes → missing ontology nodes → all papers by status

### Changed

- **`_templates/insight_note.md`** — two fixes:
  - Moved `<%* tp.file.move() %>` to after the closing `---` (previously before, which prevented Obsidian from parsing the block as YAML frontmatter — caused raw text rendering)
  - Replaced broken inline YAML comments (also broke parsing) with an HTML comment block below the frontmatter; block is invisible in reading view but shows valid options and examples for every field when editing
- **`_templates/ontology_metric.md` + all 5 metric nodes** (Cadence, Stance Time, Stride Time, Symmetry Index, Symmetry Ratio) — Referenced In query now includes a Reference Data section listing `04_Reference_Data/` notes that wikilink to the metric
- **`_templates/ontology_population.md` + all 6 population nodes** (CIDP, Foot Drop, Healthy Adults, Healthy Older Adults, Multiple Sclerosis, Parkinsons Disease) — same Reference Data addition to Referenced In
- `_setup_files/Lab Vault System Architecture.md` — updated:
  - Ontology section: clarified Referenced In now includes Reference Data for metric and population nodes
  - Processing Queue description: updated from 3 to 5 sections with per-section usage guidance
  - Insight Note Properties: added plain text YAML rule with autocomplete warning, template structure note explaining why move command must follow `---`

### Decisions

- The 7-word threshold cleanly separates ontology links from insight links and is used by both the ontology query (< 7 words) and the missing insight query (7+ words) — two sides of the same filter
- Reference Data is added to metric and population Referenced In only (not activities, methods, etc.) because reference data tables consistently wikilink their Metric and Population columns but not other fields

---

## 2026-03-17 — Better BibTeX Documentation + Zotero Team Sharing

### Added

- `_setup_files/Lab Vault System Architecture.md` — new sections:
  - **Required Zotero Plugin: Better BibTeX** — installation, citekey format, pinning recommendation
  - **Team Literature Sharing** — Zotero Groups as the shared library mechanism, what syncs through Zotero vs. Git, storage tier comparison, WebDAV alternative
- `_setup_files/QUICKSTART.md` — new Step 2: Set Up Zotero (Better BibTeX install, citekey format configuration, joining the shared group library)
- `README.md` — added Better BibTeX to prerequisites table; added **Shared Zotero Library** section explaining the Git vs. Zotero split

### Removed

- `_setup_files/Celestra.bib`, `_setup_files/My Library.bib`, `_setup_files/My Library.json` — stale exports from the old Citations plugin workflow; no longer needed since Zotero Integration connects directly to Zotero via the Better BibTeX API

### Decisions

- PDFs and `.bib` files belong in Zotero, not Git. Git stores only Obsidian notes, templates, and plugin configuration.
- Team literature sharing uses Zotero Groups (equivalent to Mendeley shared libraries). Each member syncs independently through their zotero.org account.

---

## 2026-03-17 — Removed Citations Plugin

### Removed

- **Citations plugin** (`obsidian-citation-plugin`) — fully removed from the repository; plugin files, settings, and `community-plugins.json` entry deleted
- `_templates/citations_paper_note.md` — legacy template removed; `zotero_paper_notes.md` is the sole paper note template

### Rationale

The Citations plugin was originally used for citekey resolution, `.bib` file management, and pandoc citation syntax. With Zotero Integration handling all paper note creation, Citations had no remaining role in the active workflow. Manuscripts are written in Word using the Zotero Word plugin, which manages citations independently. The Citations plugin was also the only source of a machine-specific absolute path in the repository (the `.bib` file path), which would have broken the setup for any collaborator who cloned the repo.

### Changed

- `_setup_files/Lab Vault System Architecture.md` — removed all Citations plugin references; updated plugin roles table and templates table
- `_setup_files/LLM_CONTEXT.md` — updated plugin architecture section
- `_setup_files/QUICKSTART.md` — completely rewritten to reflect that all plugins are pre-installed in the repo (no manual installation required); added Zotero Word plugin to prerequisites; simplified Steps 3–5
- `README.md` — updated prerequisites table and Step 5/6 to reflect trust-and-go plugin setup

---

## 2026-03-17 — Sub-population Strategy, Insight Explorer, Manuscript Workflow

### Added

- `03_Ontology/populations/Healthy Older Adults.md` — first dedicated sub-population node; justified by distinct normative gait values and frequency as age-matched control group
- `00_Inbox/Insight Explorer.md` — live Dataview dashboard with pre-built queries to retrieve insights by population, metric, domain, property, method, and citekey; includes query to flag insight notes with missing frontmatter fields
- `_templates/project_note.md` — new template for `05_Projects/` notes; includes Relevant Insights and Relevant Papers Dataview queries, Reference Data table, and Open Questions section; auto-moves to `05_Projects/`
- `03_Ontology/ontology_map.md` — replaced static text with live `LIST` Dataview queries for all 7 ontology categories; updates automatically as nodes are added

### Changed

- **All 27 ontology template and node files** — `## Referenced In` DataviewJS query updated to also check insight YAML frontmatter fields (`population`, `activity`, `metric`, `method`, `domain`, `property`) in addition to outgoing wikilinks; ensures insight notes show up in ontology backlinks even if no body wikilink is present
- `_setup_files/Lab Vault System Architecture.md` — added:
  - **Sub-population Handling** section documenting the 3-insight threshold rule and qualifier encoding strategy
  - **Manuscript Writing Workflow** section with step-by-step guidance for using vault content in manuscripts (Introduction/Discussion, Methods, Results, reference list building)
  - `project_note.md` added to templates table
  - Query Strategy section updated to describe Insight Explorer as the primary retrieval tool for writing
- `02_Insights/Impaired Dorsiflexion in Foot Drop.md` — restructured to match new insight template: YAML frontmatter populated with all fields, body reduced to claim + evidence prose; removed redundant `source:` field and label-value body lines

### Decisions

- Sub-population nodes are only created when 3+ insights share the same qualifier. Until then, specificity lives in insight titles (sentence form), YAML `population:` text, and parenthetical qualifiers in paper note Study Context.
- `Insight Explorer` replaces ad-hoc searches for manuscript preparation; it is the canonical entry point for retrieving vault knowledge for writing.

---

## 2026-03-11 — Initial Vault Structure Review

### Added

- `03_Ontology/metric_domains/` folder with five domain notes: Pace, Rhythm, Variability, Asymmetry, Postural Control
- `03_Ontology/properties/` populated with six property notes: Reliability, Validation, Variability, Sensitivity, Detection, Clinical Association
- `_templates/paper_note.md` — canonical paper note structure using `{{citekey}}` and `{{year}}` variables to mirror the Citations plugin template
- `_templates/ontology_population.md`
- `_templates/ontology_activity.md`
- `_templates/ontology_method.md`
- `_templates/ontology_metric.md` — includes Equation field using built-in KaTeX math rendering
- `_templates/ontology_metric_domain.md`
- `_templates/ontology_property.md`

### Updated

- `_templates/insight_note.md` — added missing `domain:` field to frontmatter
- `_templates/reference_data.md` — added baseline table structure with note about adapting columns per study
- `03_Ontology/metrics/Stride Time.md` — updated to match metric template; added Definition, Equation, Domain, Unit
- `02_Insights/Impaired Dorsiflexion in Foot Drop.md` — added YAML frontmatter block; added title heading and claim statement
- `_setup_files/Lab Vault System Architecture.md` — updated to reflect all structural decisions made during initial review

### Moved

- `Design insights.md` → `_setup_files/Design insights.md`

### Deleted

- `01_Papers/.md` — blank file created by a failed template instantiation

### Decisions Recorded

- Ontology nodes do **not** use YAML frontmatter (overhead not justified; links serve the same purpose)
- Paper note frontmatter contains only `type`, `citekey`, `year`, `status` — bibliographic metadata stays in Zotero
- Citations plugin template is configured inline in plugin settings; `_templates/paper_note.md` mirrors it and must be kept in sync manually
- `Foot Drop` remains in `03_Ontology/populations/` despite being a clinical condition rather than a population — it functions as a study group label in the literature
- Obsidian has built-in KaTeX math rendering; no plugin required for equations

---

## 2026-03-11 — Paper Note Refinement (Soulard 2021 dry run)

### Added

- `03_Ontology/activities/Dual-task Walking.md` — new activity node
- `03_Ontology/metrics/Symmetry Index.md` — new metric node with SI equation, links to Asymmetry domain
- `03_Ontology/metrics/Symmetry Ratio.md` — new metric node with SR equation, links to Asymmetry domain
- `04_Reference_Data/soulard2021SpatiotemporalGait — Intra-session Reliability.md` — first reference data note; ICC, SEM, MDC for core spatiotemporal and symmetry metrics

### Updated

- `_templates/paper_note.md` — added `Statistics:` field to Study Context
- `01_Papers/soulard2021SpatiotemporalGait.md` — corrected Study Context (removed narrative prose), fixed metric links (Asymmetry → Symmetry Index + Symmetry Ratio), corrected activity links, removed citation from Notes, linked reference data note
- `_setup_files/Lab Vault System Architecture.md` — documented Study Context authoring rules; added Statistics field to paper note example

### Decisions Recorded

- Study Context uses wikilinks and brief parentheticals only — no full sentences. Sentence-level observations belong in insight notes.
- Unresolved wikilinks are acceptable temporarily; stub notes should be created promptly for any concept that will appear across multiple papers
- Asymmetry is a metric domain; Symmetry Index and Symmetry Ratio are the specific metrics that belong to it
- Statistical methods (ICC, SEM, MDC, etc.) are linked in the Statistics field and housed as ontology nodes in `03_Ontology/methods/`

---

## 2026-03-17 — Zotero Integration Workflow + Processing Queue

### Added

- `_templates/zotero_paper_notes.md` — canonical paper note template using Nunjucks syntax for Zotero Integration plugin; replaces `paper_note.md` as the primary template for creating paper notes
- `01_Papers/kim2026InsoleDerivedPlantar.md` — first paper note created via Zotero Integration; includes color-routed highlights and persist blocks
- `01_Papers/figures/kim2026InsoleDerivedPlantar/` — embedded figures extracted during import
- `04_Reference_Data/kim2026InsoleDerivedPlantar - Smart Insole Validation.md` — reference data note with reliability (ICC) and validation (Bland-Altman) tables for spatiotemporal metrics
- `00_Inbox/Processing Queue.md` — Dataview dashboard with three sections: papers pending insight extraction (`status: reading`), unresolved ontology references (short wikilinks with no corresponding file, sourced from paper and insight notes), and all papers by status

### Updated

- `_setup_files/Lab Vault System Architecture.md`:
  - Added Plugin Roles section: Citations handles citekeys/.bib; Zotero Integration creates paper notes
  - Added Zotero Integration: How It Works section explaining import, re-import, and persist block behavior
  - Added Zotero Highlight Color Scheme table (Blue/Purple/Magenta/Red/Yellow) with section routing
  - Replaced old minimal workflow with three-phase model: In Zotero → Import + fast fill → Deferred extraction
  - Documented Processing Queue pattern and two triggers for creating insight files (on-demand vs. batch)
  - Updated Paper Notes example to reflect actual Zotero Integration template output with persist markers and auto-filled vs. manually filled fields annotated
  - Updated templates table to list `zotero_paper_notes.md` as canonical and `citations_paper_note.md` as legacy
  - Clarified `status` semantics: `reading` = imported, insight files not yet created; `processed` = all insight files created
- `04_Reference_Data/kim2026InsoleDerivedPlantar - Smart Insole Validation.md` — fixed incomplete `Citation: @` field

### Decisions Recorded

- Citations plugin and Zotero Integration coexist with distinct roles; paper notes are now created via Zotero Integration, not Citations
- Highlight color scheme: Blue = purpose/hypothesis, Purple = demographics, Magenta = methods, Red = results, Yellow = insights
- Persist blocks (`%% begin ... %%` / `%% end ... %%`) protect manually edited sections from re-import overwrite; once edited, content is permanently preserved by subsequent imports
- Insight files in `02_Insights/` should be named at reading time as wikilinks in the paper note but created later — either on-demand when cited in a manuscript, or in a batch session using the Processing Queue
- Unresolved insight wikilinks are surfaced by Obsidian's Outgoing Links panel and graph view; no separate tracking needed
- Dataview plugin required for Processing Queue queries; must be installed from Community Plugins
- Unresolved ontology references are tracked via a DataviewJS query that scans `01_Papers/` and `02_Insights/` for short wikilinks (< 7 words) with no corresponding file; insight-style sentence links are excluded by the word-count filter

---

## 2026-03-17 — Template Overhaul

### Added

- `_templates/ontology_statistic.md` — new template for statistical methods (ICC, Bland-Altman, Pearson, ANOVA, etc.); auto-moves to `03_Ontology/methods/`

### Updated

- All ontology templates now include `tp.file.move()` to auto-place files in the correct `03_Ontology/` subfolder on creation via Templater
- `_templates/insight_note.md` — removed duplicate body fields (Population, Activity, Metric, Property, Source were repeated from YAML); streamlined body to claim + Evidence + Reference Data; removed redundant `source:` field; added auto-move to `02_Insights/`
- `_templates/reference_data.md` — added auto-move to `04_Reference_Data/`; clarified `[[citekey]]` placeholder
- `_templates/ontology_metric.md` — added `Interpretation:` field (higher/lower values)
- `_templates/ontology_activity.md` — added `Common populations studied:` field
- `_templates/ontology_method.md` — added `Key specifications:` field (sampling rate, sensor type)
- `_templates/ontology_property.md` — added `Common statistics:` field
- `_templates/ontology_metric_domain.md` — added `Clinical significance:` field
- `_templates/citations_paper_note.md` — added deprecation notice; no longer in active use
- `_setup_files/Lab Vault System Architecture.md` — updated templates table with auto-move destinations; added `ontology_statistic.md`
- `00_Inbox/Processing Queue.md` — added Type → Template → Destination lookup table in Unresolved Ontology References section; fixed type detection for `## Metrics Studied` heading (was bleeding Statistics label into Metrics section)

### Decisions Recorded

- Statistics (ICC, Bland-Altman, etc.) use `ontology_statistic.md` and live in `03_Ontology/methods/` alongside measurement methods
- All templates use `tp.file.move()` so "Create new note from template" always places files in the correct folder with no manual move required
- `insight_note.md` body contains only the claim, Evidence, and Reference Data — YAML frontmatter carries all structured metadata; body duplication removed
- All ontology templates include a `## Referenced In` DataviewJS section showing papers (with year and status) and insights that link to the node; this is partially redundant with Obsidian's native Backlinks panel but adds value by filtering to papers/insights only, showing metadata, and being visible in the note body without opening the sidebar

---

## 2026-03-17 — Clinical Measure Template

### Added

- `_templates/ontology_clinical_measure.md` — new template for clinical measures, performance tests, and severity scales (e.g. Hoehn & Yahr, EDSS, TUG, Stroop, 10MWT); fields include Purpose, Administration, Score range, Interpretation, Equation (optional), MDC, MCID, Relevant populations, and Referenced In query; auto-moves to `03_Ontology/Clinical Measure/`

### Updated

- `_setup_files/Lab Vault System Architecture.md` — added `Clinical Measure/` to folder structure and templates table
- `00_Inbox/Processing Queue.md` — added Clinical Measure row to Type → Template lookup table

### Decisions Recorded

- Clinical measures live in `03_Ontology/Clinical Measure/` (already established by existing `Stroop Word Test.md`)
- Clinical measures appearing in paper notes (e.g. `[[Hoehn and Yahr]]` inside a Population entry) may be typed as "Population" by the Processing Queue's section-detection heuristic; this is a known limitation — correct manually using the Type column
- Property files do not include a Referenced In query — properties are used as plain-text YAML frontmatter fields in insight notes, not as wikilinks, so backlink queries would return no results

---

## 2026-03-17 — Ontology File Backfill

### Updated

All existing ontology files updated to match current templates:

**Populations** (`cidp.md`, `Multiple Sclerosis.md`, `Healthy Adults.md`, `Foot Drop.md`, `Parkinsons Disease.md`):
- Added `Description:` field to all
- Renamed `Clinical scale:` → `Clinical scales:` for consistency
- Fixed list formatting (added `-` bullet style)
- Added `## Referenced In` DataviewJS query to all

**Activities** (`Straight-line walking.md`, `Dual-task Walking.md`, `Turning.md`, `Foot Strikes.md`):
- Added `Common populations studied:` field to all
- Added `Description:` where missing
- Restructured `Dual-task Walking.md` to match template (was using non-standard `Related metrics:` label; added `Common secondary tasks:` as a retained extra field)
- Updated `Foot Strikes.md` from a bare definition note to full activity template structure
- Added `## Referenced In` DataviewJS query to all

**Methods** (`IMU.md`):
- Fixed heading from `# [IMU]` to `# IMU`

**Metrics** (`Stride Time.md`, `Symmetry Index.md`, `Symmetry Ratio.md`):
- Added `Interpretation:` field to all
- Moved inline interpretation notes from `Unit:` field into `Interpretation:` for SI and SR
- Added `## Referenced In` DataviewJS query to all

**Metric Domains** (`Rhythm.md`, `Pace.md`, `Variability.md`, `Asymmetry.md`, `Postural Control.md`):
- Added `Description:` field to all
- Added `Clinical significance:` field to all
- Updated `Asymmetry.md` metrics list to include `[[Symmetry Index]]` and `[[Symmetry Ratio]]`
- Added `## Referenced In` DataviewJS query to all

**Properties** (`Reliability.md`, `Validation.md`, `Detection.md`, `Clinical Association.md`, `Sensitivity.md`, `Variability.md`):
- Added `Common statistics:` field with relevant wikilinked statistics to all
- Referenced In query omitted — properties are stored as plain-text YAML in insight notes, not as wikilinks

**Clinical Measures** (`Stroop Word Test.md`):
- Fully restructured to `ontology_clinical_measure.md` template
- Added: Purpose, Administration, Score range, Interpretation, Conditions description, Relevant populations, Referenced In query

---

## 2026-03-17 — Template Heading Convention + TUG Moved

### Updated

- All ontology templates (`ontology_population.md`, `ontology_activity.md`, `ontology_method.md`, `ontology_statistic.md`, `ontology_metric.md`, `ontology_metric_domain.md`, `ontology_property.md`, `ontology_clinical_measure.md`) — replaced static placeholder headings (e.g. `# [Metric Name]`) with `# <% tp.file.title %>` so the heading is filled automatically from the filename on note creation; no manual heading edit required
- `_setup_files/Lab Vault System Architecture.md` — added Clinical Measures section to Ontology Structure; added note clarifying TUG and similar performance tests belong in `Clinical Measure/` not `activities/`; added note on Statistical methods living in `methods/`; documented `# <% tp.file.title %>` heading convention; added Referenced In exception for property nodes

### Moved

- `03_Ontology/activities/TUG.md` → `03_Ontology/Clinical Measure/TUG.md` — TUG is a standardised clinical performance test with defined scoring; belongs in Clinical Measure rather than activities

### Decisions Recorded

- All ontology template headings use `# <% tp.file.title %>` — the heading is always derived from the filename; do not type the title manually into the heading
- Performance tests with defined clinical scoring (TUG, 10MWT, 6MWT, etc.) belong in `Clinical Measure/`, not `activities/`; activities are movement task types, clinical measures are scored instruments

---
