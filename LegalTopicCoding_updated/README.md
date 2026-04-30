# Frankenstein's Bill: The Political Utility of Disjointed Legislation

This repository contains the replication code for the MPhil thesis *"Frankenstein's Bill: The Political Utility of Disjointed Legislation."* The project identifies and measures provisions within legislation that are textually unrelated to a bill's stated purpose, examining how policymakers strategically exploit this disjointedness to create ambiguity, obscure rider provisions, and advance political goals. Two section-level measures are constructed for roughly 1.75 million legislative sections drawn from the United States, the European Union, and France.

---

## Data

All raw and processed data files are stored on Google Drive (too large for GitHub):

**[Google Drive data folder](https://drive.google.com/drive/folders/1qhlCgEDZf6_V5UZm3bGnyvRdhsjHgEl5)**

Download the contents and place them inside the `data/` directory before running any script.

### Data sources

| Corpus | Source | Reference |
|---|---|---|
| United States | Billsum dataset | Kornilova & Eidelman (2019) |
| European Union | Eur-Lex decisions | Laurer & Borrett (2020) |
| France | Harvard Library Innovation Lab | Harvard Library Innovation Lab (2024) |

---

## Key variables

**`divergence_vs_title`** — TF-IDF cosine divergence between a section's text and the bill's title. A value of 0 indicates the section and title share the same vocabulary in the same proportions; a value of 1 indicates complete textual disjointedness. Computed using `text2vec` with a vocabulary capped at 3,000 terms.

**`hiddenness_textual`** — Relative section length, defined as 1 minus the proportion of the bill's total sentences contained in a given section. A section that accounts for a tiny share of the bill's text receives a high hiddenness score, meaning its content is less visible to a reader scanning the bill.

---

## Reproducing the pipeline

Run the four scripts in order. Each produces intermediate data files consumed by the next.

```
R/
├── 01_topic_coding.Rmd                 # Data ingestion, segmentation, TF-IDF, topic labels
├── 02_exploratory_analysis.Rmd         # Descriptive plots and validity regressions
├── 03_structural_descriptive_analysis.Rmd  # Salience, lobbying, DV construction
└── 04_results.Rmd                      # Fixed effects, ECM, marginal effects tables
```

1. **Install packages** — see [PACKAGES.md](PACKAGES.md) or run the quick install block at the bottom of that file.
2. **Set your Manifesto Project API key** — `03_structural_descriptive_analysis.Rmd` requires access to the Manifesto Project corpus. Register at https://manifesto-project.wzb.eu/ and set the key in your environment before knitting:
   ```r
   Sys.setenv(MANIFESTO_API_KEY = "your_key_here")
   ```
3. **Download data** from the Google Drive link above and place files in `data/`.
4. **Knit in order**: open each `.Rmd` in RStudio and knit, or run `rmarkdown::render("R/01_topic_coding.Rmd")` etc. from the project root.

All output (PDF figures, LaTeX tables) is written to `output/`.

---

## Repository structure

```
/R/             All analysis scripts (numbered, snake_case)
/data/          Placeholder — download data from Google Drive link above
/output/        Placeholder — populated when scripts are run
README.md
PACKAGES.md     Full package list with CRAN links and install instructions
.gitignore      Excludes data files and generated output
```

---

## Package dependencies

See [PACKAGES.md](PACKAGES.md) for the full list. Core dependencies: `tidyverse`, `text2vec`, `fixest`, `stargazer`, `marginaleffects`, `manifestoR`, `readODS`, `data.table`.

---

## Contact

If you use the dataset or code for your own research, feel free to reach out with questions or findings.
