<div align="center">

# BibNexus

**Software for Multi-Source Bibliographic Management, Data Cleaning, Screening, and Statistical Analysis**

[![Release](https://img.shields.io/badge/Release-v1.2.0-blue.svg)](https://github.com/bibnexus/BibNexus/releases)
[![DOI](https://img.shields.io/badge/DOI-10.6084%2Fm9.figshare.34899999-blue.svg)](https://doi.org/10.6084/m9.figshare.34899999)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-brightgreen.svg)](https://www.bibnexus.com)

**[English](README_en.md)** | **[简体中文](README_zh.md)**

<p align="center">
  <b>Website:</b> <a href="https://www.bibnexus.com">https://www.bibnexus.com</a> &nbsp;|&nbsp;
  <b>How to Cite:</b> <a href="https://www.bibnexus.com/en/citation">https://www.bibnexus.com/en/citation</a>
</p>

</div>

---

## 📌 Positioning & Core Value

**BibNexus** is a cross-platform, local-first desktop software engineered for researchers, clinical scientists, information specialists, and postgraduate scholars worldwide. Tailored for empirical methodologies across **Scientometrics**, **Science Mapping**, and **Systematic Reviews & Meta-Analyses (PRISMA 2020)**, BibNexus bridges the laborious, error-prone data curation gap between raw bibliographic exports and downstream analytical environments.

Traditional research workflows frequently suffer from fragmented database schemas, corrupted character encodings, inconsistent institutional names, destructive deduplication mishaps, unstandardized screening logs, and compliance vulnerabilities associated with uploading prospective protocols to third-party cloud servers. BibNexus delivers a self-contained, offline desktop environment: featuring 9-database multi-source ingestion, a 5-stage ROR/AI institutional affiliation and country normalization pipeline, a four-tier progressive deduplication protocol with side-by-side divergence inspection, a full-lifecycle PRISMA 2020 two-phase screening workflow with embedded PICO extraction, an arithmetic-conserved PRISMA flow diagram engine, thesaurus harmonization (`.bnvm`), and 16-dimension bibliometric statistics. All data resides in local, isolated single-file databases (`.bndb`), guaranteeing 100% offline data privacy without remote telemetry.

---

## 🚀 Why BibNexus? Resolving 5 Structural Bottlenecks

| Methodological Bottleneck | BibNexus Architecture & Breakthrough |
| :--- | :--- |
| **Heterogeneous Multi-Database Schema Drift**<br>Databases export disparate, non-standardized field tags. Merging records results in field loss and syntax corruption that breaks downstream mapping software. | **Native 9-Database Ingestion & Web of Science Field Standardization**<br>Automatically converts exports from 9 major international and Chinese databases into Web of Science standard field tags (`PT`, `AU`, `AF`, `TI`, `SO`, `DE`, `AB`, `C1`, `RP`, `PY`, etc.) for seamless ingestion. |
| **Institutional Affiliation Fragmentation**<br>Disparate spelling variants, subsidiary departments, and hospital names for the same parent university fragment institutional co-authorship networks. | **Automated 5-Stage ROR + AI Affiliation & Country Normalization**<br>Deterministic noise stripping $\to$ Right-to-left geographic anchoring (ISO 3166-1) $\to$ Embedded 110,000+ ROR knowledge base parent matching $\to$ Edge-native LLM micro-batching fallback $\to$ Web of Science bracketed reconstruction. Supports 3 institutional rollup preferences. |
| **Destructive Deduplication & False Exclusions**<br>Over-reliance on DOI misses records without persistent identifiers, while unverified title matching risks accidental deletion of distinct trials. | **Four-Tier Progressive Deduplication & Divergence Inspection**<br>Tier 1 Identifier exact matching $\to$ Tier 2 Multi-field strict matching $\to$ Tier 3 Source-level matching $\to$ Tier 4 Relaxed title-year matching with side-by-side divergence matrices and primary-record heuristics. Non-destructive Recycle Bin isolation. |
| **Screening Traceability Gaps & Accidental Decision Loss**<br>Screening in general-purpose spreadsheets lacks structured audit trails. Global undo chains indiscriminately roll back whole libraries upon minor misclicks. | **PRISMA 2020 Screening & 50-Step Local Undo Buffer**<br>Baseline reference pool freezing; Card-deck (`I`/`M`/`E` blind evaluation) & dense table views; Standardized hierarchical exclusion registry; Dedicated 50-step per-project local undo stack (pressing `Z` only reverses the current record); Embedded PICO drawer. |
| **Cloud Data Exposure & Compliance Risks**<br>Commercial cloud platforms mandate uploading prospective review protocols and unpublished literature corpora, risking institutional data privacy violations. | **Local-First Data Sovereignty (.bndb Engine)**<br>Single-file relational database containers (`.bndb`). 100% offline execution without network dependencies or telemetry, fully compliant with air-gapped laboratory and hospital network mandates. |

---

## 🌟 Core Feature Matrix

### 1. 📥 Multi-Source Academic Ingestion (9 Databases)
* **Comprehensive Academic Coverage**:
  * **International Databases**: Web of Science (TXT), PubMed (NBIB), Scopus (CSV), Embase (RIS), EndNote (CIW / RIS mixed exports);
  * **Chinese Academic Repositories**: CNKI (RefWorks), Wanfang Data (RefWorks), VIP Information (CQVIP RefWorks), Chinese Medical Journal Network (Yiigle RefWorks).
* **Ingestion-Time Standardization**: Automatically normalizes dual-layer document type hierarchies (core categories preserved alongside source-native types), parses persistent identifiers (DOI, PMID, UT, EID), and dissects author affiliation blocks.

### 2. 🏛️ Automated 5-Stage Affiliation & Country Normalization (ROR & AI)
Eliminates institutional fragmentation in scientometric collaboration networks through an algorithmic pipeline:
1. **Stage 1: Deterministic Noise Stripping**: Strips email addresses, ORCIDs, telephone/fax numbers, postal codes, and extraneous punctuation;
2. **Stage 2: Right-to-Left Geographic Anchoring**: Resolves ISO 3166-1 country codes, standardizing modern geopolitical designations (Türkiye, Czechia, KSA) and back-tracing US, Australian, and Canadian states/provinces;
3. **Stage 3: Embedded 110,000+ ROR Knowledge Base Disambiguation**: Matches academic entities against the offline Research Organization Registry using spatial-topological and token-weighted cross-scoring ($\text{Score} \ge 80$), cleanly mapping subsidiary hospitals and colleges to their parent universities;
4. **Stage 4: Edge LLM Micro-Batching Fallback**: Employs compact 20-record micro-batch inferences for unstructured, non-standard long-tail affiliations;
5. **Stage 5: Web of Science Standard Reassembly**: Re-structures addresses into standard `[Primary Institution], [Sub-units], [City/State], [Country].` while maintaining strict author-to-address square bracket associations `[Author A; Author B]`.
* **Three Institutional Rollup Preferences**: "Parent University First", "Parent University First with Affiliated Entity Following", and "Affiliated Hospital First", catering to both global academic evaluations and clinical ranking needs.

### 3. 🔁 Four-Tier Progressive Deduplication Protocol
* **Progressive Deduplication Ladder**:
  * **Tier 1: Persistent Identifier Exact Matching**: Groups records sharing identical DOIs, PubMed PMIDs, WoS UT accession numbers, or Scopus EIDs with zero false-positive risk;
  * **Tier 2: Comprehensive Multi-Field Rule**: Groups records based on "Title + Publication Year + First Author + Abstract";
  * **Tier 3: Source-Level Combinatorial Rule**: Evaluates "Title + Publication Year + First Author + Source/Journal";
  * **Tier 4: Relaxed Combinatorial Rule & Manual Verification**: Matches on "Title + Publication Year" with text fault tolerance (casing, punctuation, and whitespace insensitivity).
* **Side-by-Side Comparison Matrix**: Candidate duplicate pairs in permissive tiers are presented in an interactive matrix highlighting field discrepancies (missing abstracts, author roster variations). Evaluates metadata completeness to recommend the optimal primary record, allowing researchers to inspect differences before soft-deleting secondary duplicates to the Recycle Bin;
* **Non-Destructive Recycle Bin**: Preserves original categorization structures and enables instantaneous, fully reversible one-click restoration.

### 4. 📋 Full-Lifecycle PRISMA 2020 Screening Pipeline
* **Baseline Cohort Freezing**: Freezes the post-deduplication reference pool upon review initiation, safeguarding methodological audit trails;
* **Two-Phase Dual-Interface Screening**:
  * **Phase 1 (Title/Abstract)**: High-throughput **Card-Deck View** for rapid keyboard-driven evaluation (`I` Include, `M` Maybe, `E` Exclude with numeric reason shortcuts, `Z` Undo, `P` PICO drawer) alongside dense tabular views;
  * **Phase 2 (Full-Text)**: Side-by-side inspection of attached local PDF files or online publisher versions via DOI resolution;
* **Standardized Exclusion Reasons Registry**: Structured hierarchical taxonomy (Ineligible Population, Ineligible Intervention, Non-RCT Design, Missing Primary Outcomes, etc.) with custom color tagging and template sharing;
* **50-Step Local Undo Buffer**: Operates strictly within the current screening project, ensuring that pressing `Z` reverses only the immediate classification misclick without side effects on overall library state;
* **Detached Autonomous Screen Window (`PrismaStandalone`)**: Pops the screening interface into an independent native desktop window, enabling efficient dual-monitor workflows ("Primary Display for PDF full-text reading; Secondary Display for card-deck blind evaluation and PICO extraction");
* **Embedded In-Situ PICO Extraction Drawer**: Extracts Population (P), Intervention (I), Comparison (C), and Outcome (O) variables during full-text review, exporting structured baseline characteristic matrices directly to CSV;
* **Dynamic Arithmetic-Conserved PRISMA 2020 Flow Diagram Engine**:
  * Real-time arithmetic conservation verification: $N_{\text{Identified}} - N_{\text{Duplicates}} - N_{\text{Phase1\_Excluded}} - N_{\text{Phase2\_Excluded}} = N_{\text{Included}}$;
  * Dual-paradigm layout: Clinical 5-box standard vs. Bibliometric 4-box analysis;
  * Pre-configured themes: Classic Academic Blue, Lancet Green, and Monochrome Grayscale;
  * Export options: Vector SVG, high-resolution PNG, and publication-ready vector PDF.
* **Dual-Reviewer Blind Screening & Reliability Evaluation**: Synthesizes $2\times 2$ contingency tables, computes percent agreement $P_o$, Cohen's Kappa coefficient $\kappa$, and 95% confidence intervals, supported by third-reviewer arbitration for discrepant classifications.

### 5. 🔬 Bibliometric Lab & Thesaurus Harmonization
* **16-Dimension Macro/Micro Statistical Suite**:
  * Analyzes annual publication output, journal distributions, core authors, institutional rankings, geographic spread, and keyword frequencies;
  * Fits annual growth to non-linear Logistic growth curves;
  * Evaluates Price's Law core author threshold $M = 0.749\sqrt{N_{\max}}$, assessing the 50% community productivity benchmark;
  * Partitions Bradford's Law core, related, and peripheral journal zones ($1 : n : n^2$);
  * Toggles between Full Counting and Fractional Counting, with one-click export of structured CSV reports.
* **Thesaurus Harmonization Engine (`.bnvm`)**:
  * Standalone project format recording synonym mappings and cleanup rules for reproducible curation;
  * Standardized Title Casing algorithm protecting 21 common prepositions/conjunctions while exempting domain-specific acronyms (`fMRI`, `CRISPR-Cas9`, `mRNA`);
  * Bidirectional import and export for CiteSpace alias tables (`citespace.alias`) and VOSviewer thesaurus files (`thesaurus.txt`).

### 6. 📤 Frictionless Downstream Exports
* **Web of Science Tagged Plain Text (WOS TXT)**: Exported `.txt` files conform to Web of Science field standards (including `PT`, `AU`, `AF`, `TI`, `SO`, `DE`, `AB`, `C1`, `RP`, `PY`), ready for direct ingestion into **CiteSpace**, **VOSviewer**, **VosGraph**, **HistCite**, or R **Bibliometrix** without third-party converters;
* **Standard Academic Formats**: Exports EndNote CIW, standard RIS, and structured CSV/Excel for direct ingestion into **RevMan**, **Stata**, and **Zotero**.

### 7. 🛡️ Local-First Data Sovereignty & Privacy
* **Self-Contained Database Containers (`.bndb`)**: Each library operates as an isolated single-file database. All records, screening audits, and PDF attachment links remain exclusively on the user's filesystem;
* **100% Offline Capability**: Free from server telemetry or cloud storage requirements, operating smoothly in air-gapped and protected enterprise environments;
* **Portable Library Backups**: `.bndb` files can be archived, moved, or duplicated without risk of project cross-contamination.

---

## 💻 Download & Installation

BibNexus is distributed as a self-contained desktop package. **No external Java, Python, or database runtimes are required.**

### 1. Download Channels
* **Official Website**: <https://www.bibnexus.com/download>
* **GitHub Releases**: [https://github.com/bibnexus/BibNexus/releases](https://github.com/bibnexus/BibNexus/releases)

### 2. Platform Specifications

| Operating System | Package Format | Architecture | Minimum System Version |
| :--- | :--- | :--- | :--- |
| **Windows** | `.exe` Installer / `.zip` Portable | x64 / ARM64 | Windows 10 (Build 1809+) / Windows 11 |
| **macOS** | `.dmg` Disk Image | Apple Silicon (M1/M2/M3/M4 Series aarch64) / Intel (x86_64) | macOS 12 Monterey or later |
| **Linux** | `.AppImage` Self-Contained / `.deb` Package | x64 | Ubuntu 20.04+, Debian 11+, Fedora 36+ |

---

## 📖 In-Text Methodology Narratives (Ready to Copy)

To facilitate standardized methodological reporting in international peer-reviewed journals (SCI / SSCI / Scopus) and postgraduate dissertations, the following templates are provided:

### Template 1: Scientometrics & Science Mapping (Full Version)
> **1.2 Data Collection and Preprocessing**  
> Raw bibliographic records were retrieved on `[Search Date]` from `[Databases, e.g., Web of Science, Scopus, PubMed, CNKI, Wanfang, VIP]`, covering the publication period from `[Start Year]` to `[End Year]`, yielding `[N]` initial bibliographic records. The search query was as follows:  
> `[Insert specific search query/queries, e.g., WoS query: TS=("bibliometric*" OR "scientometric*"); CNKI query: SU=("bibliometrics" OR "knowledge mapping")]`  
> `(Note: If multiple databases are retrieved, indicate the exact query and record count for each database separately.)`  
> 
> All raw records were imported into BibNexus (version 1.2.0) `[1]` for data cleaning and standardization:  
> **(1) Automated Ingestion and Standardization**: Raw multi-source records were parsed and converted into Web of Science field formats. Author affiliations were automatically dissected and normalized using the embedded Research Organization Registry (ROR) knowledge base and ISO 3166-1 country standards, aggregating departments and subsidiary clinical units to their parent academic institutions to prevent fragmentation in institutional collaboration networks;  
> **(2) Multi-Round Tiered Deduplication**: To eliminate cross-database duplicates while strictly preventing the accidental deletion of distinct studies with identical titles, a four-tier progressive deduplication protocol was conducted: (1) **Persistent Identifier Matching**: Records were first matched exactly on persistent digital identifiers (DOI, PubMed PMID, WoS UT accession numbers); (2) **Strict Multi-Field Matching**: Unidentified records were screened using the combination of "Title + Publication Year + First Author + Abstract"; (3) **Source-Level Matching**: Remaining entries were screened using "Title + Publication Year + First Author + Source/Journal"; (4) **Relaxed Matching with Manual Discrepancy Verification**: Finally, a relaxed "Title + Publication Year" rule was executed with case, punctuation, and whitespace tolerance. Because title-and-year matching alone is relatively permissive and carries a risk of false positives (e.g., distinct brief communications or editorials published in the same year), all candidate duplicate pairs in this round were manually inspected side-by-side to verify field-level differences and designate primary records, removing `[N]` duplicate records in total;  
> **(3) Manual Eligibility Screening**: Titles and abstracts were screened to exclude non-research items (conference calls, book reviews, errata, editorials) and off-topic records (`[N]` excluded);  
> **(4) Synonym Harmonization**: Keywords were normalized for casing (Title Case) with technical acronym protection, synonyms and spelling variants were merged (e.g., merging `[e.g., artificial intelligence into AI]`), and non-informative stop words were filtered.  
> 
> Following curation, `[N]` eligible research articles were retained, exported as Web of Science plain text records, and imported into `[CiteSpace / VOSviewer / VosGraph / Bibliometrix]` for `[keyword co-occurrence, institutional collaboration, author co-authorship, and co-citation]` network analysis.

### Template 2: Systematic Reviews and Meta-Analyses (PRISMA 2020 Statement Full Version)
> **2. Study Selection, Data Extraction, and Quality Control**  
> This study strictly adhered to the PRISMA 2020 statement. Literature searches were conducted on `[Search Date]` across `[Databases, e.g., PubMed, Embase, Web of Science, and Cochrane Library]` from inception to `[Cutoff Date]`, retrieving `[N]` records. The detailed search strategy was as follows:  
> `[Insert specific search strategy/queries, e.g., PubMed query: ("pembrolizumab"[Title/Abstract] AND "NSCLC"[Title/Abstract]); Embase query: ('pembrolizumab'/exp AND 'non small cell lung cancer'/exp)]`  
> `(Note: If multiple databases are searched, indicate the exact query and record count for each database separately.)`  
> 
> Deduplication, screening, and evidence extraction were performed in BibNexus (version 1.2.0) `[1]`:  
> **(1) Tiered Deduplication**: Raw records were ingested and deduplicated via a four-tier protocol progressing from exact persistent identifier matching (DOI, PMID) to multi-field combinations (title-year-author-abstract, title-year-author-source, and relaxed title-year matching with case and punctuation tolerance). In the permissive title-year tier, candidate duplicate pairs were inspected side-by-side to verify field divergence and prevent false positive exclusion of distinct trials, eliminating `[N]` duplicate entries and leaving `[N]` records for initial screening;  
> **(2) Two-Phase Blind Screening and Reliability Evaluation**: Two reviewers independently conducted blinded title and abstract screening, excluding `[N]` ineligible records. Full texts were subsequently retrieved and reviewed in duplicate, with specific exclusion reasons recorded (e.g., ineligible intervention, non-RCT design, missing primary outcomes), excluding `[N]` studies. Inter-rater agreement achieved a Cohen's kappa of `[0.86]` (95% CI: `[0.82–0.90]`, percent agreement `[96.5%]`), indicating almost perfect reliability. Discrepancies were arbitrated by a third senior reviewer;  
> **(3) Evidence Extraction**: Study characteristics (participants, interventions, comparators, outcomes) were extracted from the `[N]` included studies using the integrated PICO drawer to generate baseline characteristic tables. The complete screening process is presented in the PRISMA 2020 flow diagram (Figure 1).

---

## 📚 Citation Entries

When utilizing BibNexus in your academic manuscripts, dissertations, or research projects, please cite:

### 1. APA 7th Edition (Standard for International SCI / SSCI / Scopus Journals)
```text
Lu, H. (2026). BibNexus: Software for Multi-Source Bibliographic Management, Data Cleaning, Screening, and Statistical Analysis (Version 1.2.0) [Computer software]. figshare. https://doi.org/10.6084/m9.figshare.34899999
```

### 2. GB/T 7714-2015 Format (Chinese Core Journals and Theses)
```text
[1] 陆欢. BibNexus: 多源题录管理、数据清洗、文献筛选与统计分析软件 [CP/OL]. (2026-11-03)[引用日期: 2026-11-04]. https://doi.org/10.6084/m9.figshare.34899999.
```

### 3. BibTeX Entry (LaTeX / Overleaf Compilation)
```bibtex
@software{bibnexus_2026,
  author       = {Lu, Huan},
  title        = {{BibNexus: Software for Multi-Source Bibliographic Management, Data Cleaning, Screening, and Statistical Analysis}},
  month        = nov,
  year         = 2026,
  publisher    = {figshare},
  version      = {1.2.0},
  doi          = {10.6084/m9.figshare.34899999},
  url          = {https://doi.org/10.6084/m9.figshare.34899999}
}
```

### 4. IEEE Style
```text
H. Lu, "BibNexus: Software for Multi-Source Bibliographic Management, Data Cleaning, Screening, and Statistical Analysis," version 1.2.0, figshare, 2026. doi: 10.6084/m9.figshare.34899999.
```

---

## 💬 Support & Community

* **Website**: <https://www.bibnexus.com>
* **How to Cite**: <https://www.bibnexus.com/en/citation>
* **Customer Support**: <https://www.bibnexus.com/contact>
* **Issue Tracker**: Bug reports and feature suggestions are welcomed via [GitHub Issues](https://github.com/bibnexus/BibNexus/issues).

---

## 📄 License Notice

BibNexus is proprietary software. All rights reserved. This public repository is maintained exclusively for distributing compiled binaries, release packages, user manuals, and academic citation references. Decompilation, disassembly, unauthorized modification, or secondary commercial distribution of executable binaries is strictly prohibited without explicit prior written authorization.
