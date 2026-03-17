## Papers Pending Insight Extraction

Papers with `status: reading` have been imported and reviewed — insight names are written in the note as wikilinks — but the actual insight files in `02_Insights/` have not been created yet.

```dataview
TABLE year, status
FROM "01_Papers"
WHERE status = "reading"
SORT year DESC
```

**To process a paper from this list:**
1. Open the paper note
2. Open the **Outgoing Links panel** (right sidebar) — unresolved links are listed there
3. For each unresolved insight wikilink: click to create the file, fill YAML frontmatter, write one sentence using the yellow highlight text below it as a draft
4. Set `status: processed` when done

---

## All Papers by Status

```dataview
TABLE year, status
FROM "01_Papers"
SORT status ASC, year DESC
```
