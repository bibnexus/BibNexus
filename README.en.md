# BibNexus

**English | [简体中文](./README.md)**

**Multi-source Merging · Data Cleaning · Built for Bibliometrics**

Website: <https://www.bibnexus.com>

BibNexus is a local desktop application for researchers, purpose-built to solve the dirtiest, most time-consuming, and most error-prone part of your workflow: **the gap between exporting records from a database and having records you can actually use** in bibliometrics, systematic reviews, meta-analyses, or knowledge mapping.

It takes raw records from different databases — each with its own format, messy fields, and plenty of duplicates — and turns them into a clean, standardized, reusable local library, so you can move on to analysis and writing with confidence. This is exactly the step that EndNote, Zotero, CiteSpace, and VOSviewer never did well for you. BibNexus focuses on doing it to the highest standard.

---

## Bibliometrics looks like it starts with maps — it actually starts with data

Whether a record file is clean directly affects your keyword co-occurrence, institutional collaboration, author collaboration, country distribution, source statistics, and reference analysis — and ultimately whether you can explain your results.

More practically, many bibliometric studies can no longer rely on data from a single database. Relying on one source (say, Web of Science alone) risks narrow search coverage, incomplete source coverage, and unrepresentative samples — problems that easily become fatal flaws during submission and peer review.

So, **merge-and-clean across multiple databases is moving from "optional enhancement" to a basic step in many projects**. Reviewers rarely ask whether your maps look good. They ask the more fundamental questions:

- Why only this database?
- Were other sources missed?
- How were duplicate records handled?
- How were author, institution, country, and reference fields from different sources unified?

If these questions are not answered at the data stage, no map will hold up. **BibNexus is the tool that guards this data gateway for you.**

---

## Sound familiar?

- You exported records from Web of Science, Scopus, PubMed, and CNKI — all in different formats, and merging them is a mess.
- The same paper appears several times across databases; manual deduplication is exhausting and you are afraid of deleting the wrong one.
- Author affiliations mix full names and abbreviations; country names mix English and Chinese; institutional names are too dirty to count.
- A project, a review, a team project — each deserves its own library, but everything is piled into one file and it gets messier by the day.
- After all that work, the export format does not match your analysis software, and you have to fix it manually again.

BibNexus exists to end this repetitive drudgery.

---

## What BibNexus does for you

### 📥 Import from major databases in one place
Import record files exported from these sources with automatic format detection — it tells you how many records were imported, which failed, and why:

- **International databases**: Web of Science (plain text), Scopus (CSV), PubMed (nbib), Embase (RIS), EndNote (RIS)
- **Chinese databases**: CNKI, Wanfang, VIP, Yiigle (RefWorks format)

### 🧹 Cleaned on import, no rework
The most troublesome fields are cleaned the moment records enter your library:

- Author address standardization
- Institution name extraction
- Reference format standardization
- Country/region name unification
- Document type normalization

No need to fix records one by one after import.

### 🗂️ Multiple libraries, fully isolated
One library per systematic review, one per team project, one per historical project — or separate libraries for Chinese and English sources. Organize however you like. Each library's categories, favorites, deduplication results, and trash are completely independent — **records never leak or mix across libraries**.

### 🔍 Search that finds exactly what you need
- **Quick search**: instantly locate a paper; clearing the query restores your previous browsing state.
- **Advanced search**: combine year, author, source, keywords, DOI, document type, and more; save results as named, revisitable search sets.

### ✅ Screening workflow with clear structure
Systematic reviews and meta-analyses require going through titles and abstracts one by one and deciding inclusion vs. exclusion. BibNexus brings this workflow into the workspace:

- Mark read/unread; browsed records are marked read automatically
- Custom screening status names to match your inclusion/exclusion criteria
- Batch-set screening status for a selection with right-click
- Filter by read/unread or screening status to track progress at a glance

### 🔁 Deduplication — see before you act
Duplicate groups are found according to the rules you choose (strong identifiers such as DOI/WOS ID/PubMed ID/Scopus ID first, or custom field combinations). Review the differences within each group, pick the record to keep, then deduplicate in bulk with confidence. Deduplication runs in the background — no UI freeze — and deleted records can be recovered.

### ✏️ Batch editing, one pass for a whole batch
Backfill sources, replace keywords, clean author fields, swap fields, append/prepend/replace/clear text, handle capitalization… all in one pass for a batch of records, with a clear report of how many succeeded, skipped, and failed. System fields are protected from accidental changes.

### 🔤 Vocabulary merging, so statistics are not skewed by spelling variants
The same institution written as "Harvard University", "Harvard Univ.", or "哈佛大学"; the same keyword with different plural forms, capitalization, or abbreviations — if not merged, co-occurrence, collaboration, and distribution statistics are split into several buckets and your conclusions drift. The vocabulary merging workbench tackles this most hidden trap in bibliometrics:

- Import institution, country, keyword terms from the library and organize merge rules and stop words offline
- Import existing rule files from CiteSpace and VOSviewer — no need to start from scratch
- Built-in English normalization (abbreviations, special terms) to reduce manual comparison
- Results can be **written back to the library** (undoable) or **exported by item** as CiteSpace merge/exclude tables, Bibliometrix synonyms/stop words, and VOSviewer merge files, ready for downstream tools

### 🗑️ Deletion is reversible
Soft-deleted records go to the trash, organized by their pre-deletion categories. Restore individually, restore a whole category, or restore to a chosen category. Core operations support undo/redo, and the history is visible in the title bar.

### 📊 Local statistics workbench
Want to know "what's actually in this library" and "is the cleaned data distribution reliable"? Select a library and scope, and generate single-dimension statistics in one click: record counts, year, source, author, institution, country/region, funding agency, references, and more.

### 📤 Export-ready for downstream tools
Export your cleaned records in the formats downstream tools expect — no manual conversion:

- **Web of Science tagged plain text (Tagged TXT)** — the core exchange format for bibliometric workflows; directly readable by CiteSpace, VOSviewer, and Bibliometrix.
- **EndNote CIW**

Export single records, a multi-selection, a whole library, a selected category, all favorites, or a search result set; large batches are split into files automatically with cross-platform-stable filenames.

---

## Why BibNexus

- **Local-first, data under your control**: all records live in library files on your own computer. Nothing is uploaded to the cloud — privacy and data security stay in your hands.
- **One thing done exceptionally well**: no scope creep — only record governance: accurate imports, thorough cleaning, reliable deduplication, smooth exports.
- **Dense but not crowded**: the three-pane workspace (library tree on the left, record table in the middle, detail panel on the right) is designed for long-term, high-frequency use — calm, professional, easy to scan.
- **Bilingual, light and dark themes**: Simplified Chinese and English UI, light/dark/system themes, and accent color selection for comfortable long sessions.
- **Cross-platform**: Windows, macOS, Linux.

---

## Getting started

BibNexus is a local desktop application for Windows, macOS, and Linux. Download it from the website:

Website: <https://www.bibnexus.com>

## How to cite

If BibNexus has helped your research, we welcome a citation in your paper. Below are reference templates for describing BibNexus in the Methods section. Adjust the version number and details to match your actual use.

We recommend citing the references below. Citation is not required for paid users; for free users, failure to cite constitutes a license violation.

**One-sentence example**

> This study used BibNexus, a multi-database bibliographic data management tool developed by Yiku Research [1], to import, standardize, deduplicate, and export bibliographic records, ensuring the completeness and consistency of the reference data.

**I. Complete version**

> In this study, BibNexus (v1.0.2), developed by Yiku Research, was used for bibliographic data management and cleaning [1]. BibNexus is a multi-database bibliographic data management tool that supports importing records exported from CNKI, Wanfang, and VIP, and normalizing format differences across platforms. The workflow was as follows: (1) after searching in CNKI, Wanfang, and VIP, record files were batch-imported into BibNexus; (2) multiple deduplication passes were run with criteria ranging from strict to lenient (combinations of title, author, year, etc.), and records judged as duplicates were moved to the BibNexus trash; (3) the title, abstract, keywords, and other information of every record were reviewed, with full texts consulted when necessary, and records not meeting the inclusion criteria were moved to the trash; (4) the final retained records were exported following the Web of Science Core Collection field naming conventions, so that CiteSpace and VOSviewer could recognize them directly for bibliometric analysis and mapping.

**II. Concise version**

> This study used BibNexus (v1.0.2), a multi-database bibliographic data management tool developed by Yiku Research [1], to batch-import and standardize records from CNKI, Wanfang, and VIP, remove duplicates, and, after manual screening, export records following the Web of Science Core Collection field naming conventions for bibliometric analysis and mapping in CiteSpace and VOSviewer.

**III. Minimal version**

> This study used BibNexus [1], developed by Yiku Research, to import, standardize, deduplicate, and export records from multiple platforms in preparation for subsequent bibliometric analysis.

**IV. References (choose one according to your journal's requirements)**

*GB/T 7714-2015 (Chinese journals)*

```text
LU H. BibNexus: multi-database bibliographic data management and cleaning[CP/OL]. Zenodo, 2026. https://doi.org/10.5281/zenodo.21561666.
```

*APA 7th edition*

```text
Lu, H. (2026). BibNexus: Multi-database bibliographic data management and cleaning [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.21561666
```

*MLA 9th edition*

```text
Lu, Huan. BibNexus: Multi-database Bibliographic Data Management and Cleaning. Computer software, Zenodo, 2026, doi:10.5281/zenodo.21561666.
```