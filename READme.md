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

| Gene | Disorder |
|--------|--------|
| 16pDel | Autism spectrum |
| ANKRD11 | KBG syndrome |
| ASXL1 | Bohring-Opitz syndrome |
| CHD7 | CHARGE syndrome |
| CHD8 | Intellectual developmental disorder with autism and macrocephaly |
| Dup7 | Chromosome 7q11.23 duplication syndrome |
| DYRK1A | Intellectual developmental disorder, autosomal dominant 7 |
| EHMT1 | Kleefstra syndrome 1 |
| EZH2 | Weaver syndrome |
| FHS | Floating-Harbor syndrome |
| HNRNPK | Au-Kline syndrome |
| KANSL1 | Koolen-De Vries syndrome |
| KMT2C | Kleefstra syndrome 2 |
| KMT2D_2017 | Kabuki syndrome 1 |
| KMT2D_2026 | Kabuki syndrome 1 |
| MN1 | CEBALID syndrome |
| NSD1 | Sotos syndrome |
| SMARCA2 | Nicolaides-Baraitser syndrome |
| SRCAP | Developmental delay, hypotonia, musculoskeletal defects, and behavioral abnormalities |
| Williams | Williams-Beuren syndrome |

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
      → My Hubs
          → Add Hub
```

and enter:

```text
https://raw.githubusercontent.com/<user>/<repo>/<branch>/hub.txt
```

Example:

```text
https://raw.githubusercontent.com/prajkta9/ucsc-methylation-test/main/EpigenCentralHub20_2/hub.txt
```

---

## Citation

If you use this resource, please cite:

**EpigenCentral**
https://epigen.ccm.sickkids.ca/

as well as the original publications describing each episignature.

---

## Author

**Prajkta Kallurkar**  
The Hospital for Sick Children (SickKids)  
Toronto, Canada

For questions or suggestions:

📧 prajkta.kallurkar@sickkids.ca