# Highlighting Guidelines

This file defines what to highlight in Zotero and why. Poor highlighting discipline is the most common source of vault clutter — Yellow highlights that cannot be converted into insight notes accumulate and create a false sense of progress.

---

## Color Scheme Reference

| Color | Section it populates | What to highlight |
|---|---|---|
| Blue | Purpose / Hypothesis | The paper's stated aim and hypothesis — usually one or two sentences in the introduction |
| Purple | Participant Demographics | Age, sex, N, diagnostic criteria, inclusion/exclusion — specific numbers only |
| Magenta | Methods Details | Device specs, protocol parameters, signal processing steps, statistical model details |
| Red | Results | Specific numerical findings, statistical outcomes, table summaries |
| Yellow | Key Insights Extracted | Citable findings from this paper that you believe and could put in a manuscript |
| Orange | Follow-up Citations | Claims cited from other papers that you want to chase — breadcrumbs to the next paper |

---

## Yellow: The Discipline Problem

Yellow is the most abused color because it feels productive to highlight interesting text. The rule is strict:

> **Only highlight in Yellow if you could write the insight note title right now, in one sentence, as a declarative claim.**

If you cannot phrase it as a claim immediately, do not highlight it. Read it, let it inform your understanding, and move on.

---

## The Three Types of Text — Only One Belongs in Yellow

### Type 1 — Background theory and study rationale
This is text the authors wrote to justify why their study was worth doing. It is interesting while you are reading but is not a citable finding from this paper.

Examples of what NOT to highlight:
- *"Gait variability has been interpreted as an indirect expression of dynamic motor control..."*
- *"Two aspects limit the collection of gait data in realistic clinical settings..."*
- *"Wearable sensors may improve the clinical applicability of gait analysis..."*

These sentences describe the landscape the paper is situated in. They are not findings. Do not highlight them in Yellow.

### Type 2 — Claims sourced from other papers
Introductions and discussions are full of citations to prior work. If the authors write *"a value of 2.6% has been proposed as a reliable upper limit for CoV stride time (König et al., 2016),"* the citable source is König 2016, not the paper you are currently reading. Highlighting it in Yellow creates an insight note attributed to the wrong paper.

If the claim is important enough to extract, find and add the source paper to your library instead.

### Type 3 — Findings from this paper ✓
This is the only category that belongs in Yellow. These are results or conclusions that this paper established, that you believe, and that you could cite in a manuscript.

Examples of valid Yellow highlights:
- *"Reliable estimation of gait variability CoV required fewer than 15 strides in neurological groups"*
- *"Algorithmic turn excision can fail and produce misleadingly elevated CoV values"*
- *"Gait variability reliability was substantially lower than reliability of mean spatiotemporal parameters"*

A well-processed paper typically yields **3–6 Yellow highlights**. If you have more than 8, review them against the criteria above.

### Type 4 — Claims from cited papers you want to chase → Orange

Reading one paper opens a trail to others. When a paper cites a finding that is important enough to follow up on — a threshold, a normative value, a method you want to understand — highlight it in **Orange**.

Orange does not mean "I believe this claim." It means "I need to find and read the source paper." Orange highlights populate the **Follow-up Citations** section at the bottom of the note. Add a Zotero comment with the specific paper or author to find.

Example:
> *(p. 2) a value of 2.6% [2.3–3.1] has been proposed as a reliable upper limit for CoV stride time in physiological gait (König et al., 2016b).*
> - Find: König 2016b — normative CoV threshold paper

This keeps the context of *why* you want to read it attached to the breadcrumb. When you eventually add and process König 2016, you will know exactly why it was flagged and from which paper the trail started.

---

## Follow-up Citations — What Belongs and What Does Not

The Follow-up Citations section is for **papers you intend to find and read**. It is not a general notes field.

### What belongs
- A sentence citing a specific paper, where that paper contains a finding or method you want to understand in depth
- Each entry should have a `Find:` comment identifying the paper and why it matters

```
- (p. 2) Gait variability increases with MS disease severity (Chee et al., 2021)
  - Find: Chee 2021 — variability changes across disease course
```

### What does not belong

**Background statements with no specific paper to chase:**
> *"Walking is one of the most valued functions in people with MS (Heesen et al., 2008)"*

If you do not intend to read Heesen 2008 specifically, do not put this here. Background context that informed your reading does not need to live anywhere in the vault.

**Insight titles written as Note: comments:**
> *"- (p. 5) PwMS walk slower than controls.*
> *  - Note: [[People with MS have reduced walking speed compared to healthy adults]]*"

This is a common mistake. If you have identified an insight worth extracting, write the wikilink at the **top of Key Insights**, not as a Note comment in Follow-up Citations or anywhere else in the highlight block.

**General disease facts with no retrieval value:**
> *"The majority of people with RRMS transition to SPMS (Koch et al., 2010)"*

This is background you absorbed while reading. It does not need to be in the vault.

### The test
Before adding an entry to Follow-up Citations, ask: *"Do I intend to add this specific paper to Zotero and process it?"* If the answer is no, do not add it.

---

## The Insight Note Title Test

Before highlighting in Yellow, ask: **can I write a one-sentence declarative claim right now?**

A valid insight note title:
- Names a subject — a population, metric, or phenomenon
- Makes a specific claim — not a description of what the paper did
- Is manuscript-ready — you could paste it into a discussion section and it would make sense
- Is attributable to this paper — not a citation the authors used

| Text | Valid? | Reason |
|---|---|---|
| *"CoV stride time was highest in ataxic subjects"* | Yes | Specific finding, attributable to this paper |
| *"Gait variability is considered to contain portions of neuromuscular noise"* | No | Background theory, not a finding |
| *"A value of 2.6% has been proposed as an upper limit for CoV stride time (König 2016)"* | No | Sourced from another paper |
| *"15 strides were sufficient for reliable CoV estimation in movement disorder groups"* | Yes | Specific finding, attributable to this paper |

---

## When You Disagree With a Claim

Sometimes you highlight something as interesting during a first read, then later — after your own analysis — conclude the claim does not hold.

There are two distinct scenarios, and they call for different responses.

---

### Scenario A — You disagree and have no use for the claim

You read it, found it interesting, ran your own analysis, now disagree, and have no need to cite it in a manuscript as a counterpoint.

**Action: drop it.** Do not create the insight note. Leave the raw highlight in Key Insights without converting it to a wikilink. If the disagreement is worth recording, add a note in the paper note's **Notes** section:

```
## Notes
Our analysis did not replicate the <15-stride finding in healthy older adults.
Kroneberg's HE cohort required 16–20 strides, consistent with the >50-stride recommendation.
```

---

### Scenario B — You disagree but need to cite it as a contrasting finding

This is the more common scientific situation. Manuscripts often position findings against prior work: *"Kroneberg et al. found 15 strides were sufficient in movement disorder groups, however our analysis found 25 strides necessary in healthy older adults, consistent with the broader recommendation of >50 strides."*

You need Kroneberg's claim in the vault to write that sentence — but it must be flagged so it never gets treated as settled knowledge.

**Action: create the insight note with `contested: true`.**

```yaml
type: insight
population: Healthy Older Adults
metric: Coefficient of Variation
domain: Variability
property: Reliability
method: IMU
citekey: kroneberg2019LessMore
contested: true
```

In the note body, state the paper's claim, explain the disagreement, and cross-link to your counter-insight:

```
Gait variability CoV stabilises within 15–20 strides in movement disorder groups
but requires up to 20 strides in healthy older adults.

Evidence:
Kroneberg et al. found R > 0.8 correlation reached by the 10th stride in ATX and PD,
but by the 16th–20th stride in ET and HE. Our lab's analysis found 25 strides necessary
in healthy older adults, consistent with König et al.'s recommendation of >50 strides.
Contested by: [[Reliable CoV estimation requires at least 25 strides in healthy older adults]]
```

Then create the counter-insight as a separate note, cross-linking back:

```yaml
citekey: [your own paper when published]
```

```
Reliable gait variability CoV estimation requires at least 25 strides in healthy older adults.

Evidence:
Our analysis found... This contrasts with Kroneberg et al., who reported stabilisation
by the 15th stride in movement disorder groups.
Contrasts with: [[Gait variability CoV stabilises within 15-20 strides in movement disorder groups]]
```

This gives you both claims, attributed to their sources, ready to cite in a manuscript — and the `contested: true` flag ensures the Kroneberg claim is never accidentally treated as something you endorse.

---

### Querying contested insights

You can find all contested insights with a Dataview query in the Insight Explorer or any project note:

```dataview
TABLE population, metric, citekey
FROM "02_Insights"
WHERE contested = true
```

---

### What not to do

Do not create an insight note without the `contested` flag and add a disclaimer in the body like *"Note: we are not sure this is true."* Contested claims without a flag can resurface in Insight Explorer results and be cited in manuscripts without the skepticism attached.

---

## The Zotero Comment Field

When you do highlight something in Yellow, immediately right-click and add a comment. Write your own framing of the claim in plain language — not a paraphrase of the text, but the sentence you would write in a manuscript. Use the double square brackets in your comment to add the insight link at the same time.

> **Before**: *"despite low repeatability according to ICC, only marginal absolute changes in parameters of gait variability occur at group level between the 10th and 40th stride"*
>
> **Your comment**: *"Gait variability CoV stabilises by the 10th stride in neurological groups, making short clinical walks sufficient for assessment"*

The comment imports directly into the Key Insights section alongside the highlight. It becomes the draft for your insight note title. If you cannot write the comment, reconsider whether the highlight should be Yellow at all.
