# EpigenCentral DNA Methylation Episignature UCSC Track Hub

A UCSC Genome Browser Track Hub for visualizing curated DNA methylation (DNAm) episignatures from **EpigenCentral**.

This repository contains:

- UCSC Track Hub configuration files
- UCSC Track Hub bigBed file
- HTML documentation for the track
- UCSC-compatible filtering and visualization settings

## About EpigenCentral

EpigenCentral is a research resource for DNA methylation episignatures associated with rare genetic disorders.

🔗 https://epigen.ccm.sickkids.ca/

---

## Features

### Visualization

Each CpG is displayed as a colored genomic feature:
Delta beta values are calculated as mean methylation in cases minus mean methylation in controls (deltaBeta = Cases − Controls). 
Positive deltaBeta values indicate increased methylation in cases (Gain), whereas negative deltaBeta values indicate decreased methylation in cases (Loss).

- **Orange** (`255,95,1`) = gain of methylation
- **Blue** (`0,114,235`) = loss of methylation

When a CpG belongs to multiple episignatures, the displayed color is determined by the episignature with the largest absolute methylation effect size (largest absolute deltaBeta).

### Views

| View | Display |
|--------|----------|
| Dense | Colored bars only |
| Pack | Colored bars with CpG probe IDs |
| Full | Colored bars with CpG probe IDs |

### Mouse-over Information

Hovering over a CpG displays:

- Dominant episignature
- Direction of methylation change
- Delta beta value

Example:

```text
NSD1|Loss|-0.346
```

### Item Details Page

Clicking a CpG displays:

- Maximum absolute deltaBeta
- Dominant episignature
- OMIM identifier
- Number of overlapping episignatures
- List of overlapping episignatures
- Dynamic comparison table

The comparison table contains:

- Gene
- Disorder
- OMIM ID
- Direction of methylation
- Delta beta
- Adjusted p-value
- Multiple-testing correction method

---

## Included Episignatures

| Gene | Disorder | OMIM | Reference
|--------|--------|--------|--------|
| 16pDel | Autism spectrum | https://omim.org/entry/611913 | https://pubmed.ncbi.nlm.nih.gov/31311581/ |
| ANKRD11 | KBG syndrome | https://omim.org/entry/148050 | https://pubmed.ncbi.nlm.nih.gov/36440975/ |
| ASXL1 | Bohring-Opitz syndrome | https://omim.org/entry/605039 | https://pubmed.ncbi.nlm.nih.gov/35361921/ |
| CHD7 | CHARGE syndrome | https://omim.org/entry/214800 | https://pubmed.ncbi.nlm.nih.gov/28475860/ |
| CHD8 | Intellectual developmental disorder with autism and macrocephaly | https://omim.org/entry/615032 | https://pubmed.ncbi.nlm.nih.gov/31311581/ |
| Dup7 | Chromosome 7q11.23 duplication syndrome | https://omim.org/entry/609757 | https://pubmed.ncbi.nlm.nih.gov/26166478/ |
| DYRK1A | Intellectual developmental disorder, autosomal dominant 7 | https://omim.org/entry/614104 | https://pubmed.ncbi.nlm.nih.gov/34345024/ |
| EHMT1 | Kleefstra syndrome 1 | https://omim.org/entry/610253 | http://dx.doi.org/10.20517/jtgg.2020.23 |
| EZH2 | Weaver syndrome | https://omim.org/entry/277590 | https://pubmed.ncbi.nlm.nih.gov/32243864/ |
| FHS | Floating-Harbor syndrome | https://omim.org/entry/136140 | https://pubmed.ncbi.nlm.nih.gov/33909990/ |
| HNRNPK | Au-Kline syndrome | https://omim.org/entry/616580 | https://pubmed.ncbi.nlm.nih.gov/36130591/ |
| KANSL1 | Koolen-De Vries syndrome | https://omim.org/entry/610443	| https://pubmed.ncbi.nlm.nih.gov/38282074/ |
| KMT2C | Kleefstra syndrome 2 | https://omim.org/entry/617768 |	https://pubmed.ncbi.nlm.nih.gov/39013459/ |
| KMT2D_2017 | Kabuki syndrome 1 | https://omim.org/entry/147920 | https://pubmed.ncbi.nlm.nih.gov/28475860/ |
| KMT2D_2026 | Kabuki syndrome 1 | https://omim.org/entry/147920 | https://pubmed.ncbi.nlm.nih.gov/42134323/ |
| MN1 | CEBALID syndrome | https://omim.org/entry/618774 | https://pubmed.ncbi.nlm.nih.gov/40280028/ |
| NSD1 | Sotos syndrome | https://omim.org/entry/117550 | https://pubmed.ncbi.nlm.nih.gov/26690673/ |
| SMARCA2 | Nicolaides-Baraitser syndrome | https://omim.org/entry/601358 | https://pubmed.ncbi.nlm.nih.gov/31288860/ |
| SRCAP | Developmental delay, hypotonia, musculoskeletal defects, and behavioral abnormalities | https://omim.org/entry/619595 | https://pubmed.ncbi.nlm.nih.gov/33909990/ |
| Williams | Williams-Beuren syndrome | https://omim.org/entry/194050 | https://pubmed.ncbi.nlm.nih.gov/26166478/ |

---

## Filtering Options

### Episignature Filter

Users can select one or more episignatures to identify shared CpGs across disorders.

Examples:

- NSD1
- CHD8
- 16pDel
- CHD8 + 16pDel
- KANSL1 + NSD1 + KMT2D

The filter returns CpGs overlapping all selected episignatures.

### Overlap Filter

Users can filter by:

```text
Number of overlapping episignatures
```

to prioritize CpGs that are shared among multiple disorders.

---

## Repository Structure

```text
.
├── hub.txt
├── genomes.txt
├── trackDb.txt
├── episignatures.html
├── episignatures.bb
└── README.md
```

---

## UCSC Track Hub Files

### hub.txt

Defines the Track Hub metadata.

### genomes.txt

Specifies the genome assembly and corresponding track database.

Current assembly:

```text
hg38
```

### trackDb.txt

Controls:

- Track appearance
- Colors
- Dynamic tables
- Mouse-over fields
- Episignature filters
- Overlap filters

### episignatures.html

Track documentation displayed within UCSC Genome Browser.

---

## Loading the Hub in UCSC

Navigate to:

```text
My Data
  → Track Hubs
      → Connected Hubs
          → Add Hub (raw data link for hub.txt github file)
```

and enter:

```text
https://raw.githubusercontent.com/<user>/<repo>/<branch>/hub.txt
```

Example:

```text
https://raw.githubusercontent.com/ccmbioinfo/EpigenCentral-UCSC-Genome-Browser/refs/heads/main/hub.txt
```

---

## Citation

If you use this resource, please cite:

**EpigenCentral**
https://epigen.ccm.sickkids.ca/

as well as the original publications describing each episignature.

