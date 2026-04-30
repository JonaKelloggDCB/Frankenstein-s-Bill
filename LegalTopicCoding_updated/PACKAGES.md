# Package Dependencies

All packages are loaded via `pacman::p_load()` in `R/01_topic_coding.Rmd`, and via `suppressPackageStartupMessages({library(...)})` in `R/04_results.Rmd`. Install `pacman` first if not present:

```r
install.packages("pacman")
```

## Core packages

| Package | Purpose | CRAN |
|---|---|---|
| `tidyverse` | Data wrangling and plotting | https://cran.r-project.org/package=tidyverse |
| `dplyr` | Data manipulation | https://cran.r-project.org/package=dplyr |
| `tidyr` | Reshaping data | https://cran.r-project.org/package=tidyr |
| `stringr` | String operations | https://cran.r-project.org/package=stringr |
| `purrr` | Functional programming | https://cran.r-project.org/package=purrr |
| `readr` | CSV import | https://cran.r-project.org/package=readr |
| `tibble` | Tibble creation | https://cran.r-project.org/package=tibble |
| `lubridate` | Date parsing | https://cran.r-project.org/package=lubridate |

## NLP / text

| Package | Purpose | CRAN |
|---|---|---|
| `text2vec` | TF-IDF and vocabulary building | https://cran.r-project.org/package=text2vec |
| `Matrix` | Sparse matrix operations | https://cran.r-project.org/package=Matrix |
| `tokenizers` | Sentence tokenisation | https://cran.r-project.org/package=tokenizers |

## Data I/O

| Package | Purpose | CRAN |
|---|---|---|
| `jsonlite` | JSONL parsing | https://cran.r-project.org/package=jsonlite |
| `data.table` | High-performance joins | https://cran.r-project.org/package=data.table |
| `readODS` | ODS (LibreOffice) import | https://cran.r-project.org/package=readODS |
| `janitor` | Column name cleaning | https://cran.r-project.org/package=janitor |
| `rvest` | Web scraping | https://cran.r-project.org/package=rvest |
| `httr2` | HTTP requests | https://cran.r-project.org/package=httr2 |

## Models and output

| Package | Purpose | CRAN |
|---|---|---|
| `fixest` | Fixed-effects models (feols) | https://cran.r-project.org/package=fixest |
| `stargazer` | LaTeX regression tables | https://cran.r-project.org/package=stargazer |
| `sandwich` | Robust standard errors | https://cran.r-project.org/package=sandwich |
| `lmtest` | Coefficient tests | https://cran.r-project.org/package=lmtest |
| `marginaleffects` | Marginal effects / AMEs | https://cran.r-project.org/package=marginaleffects |
| `modelsummary` | Model summary tables | https://cran.r-project.org/package=modelsummary |
| `knitr` | Table formatting | https://cran.r-project.org/package=knitr |
| `kableExtra` | LaTeX table extensions | https://cran.r-project.org/package=kableExtra |

## Visualisation

| Package | Purpose | CRAN |
|---|---|---|
| `ggplot2` | Plots | https://cran.r-project.org/package=ggplot2 |
| `hexbin` | Hex-bin plots | https://cran.r-project.org/package=hexbin |

## External API

| Package | Purpose |
|---|---|
| `manifestoR` | Manifesto Project API (requires `MANIFESTO_API_KEY` environment variable) |
| `mall` | LLM-assisted text classification |
| `ollamar` | Local Ollama API client |
| `ellmer` | LLM interface layer |
| `reticulate` | Python interoperability |

## Quick install

```r
install.packages(c(
  "tidyverse", "jsonlite", "data.table", "stringr", "purrr", "tibble",
  "rvest", "httr2", "reticulate", "tokenizers",
  "text2vec", "Matrix",
  "readODS", "janitor",
  "fixest", "stargazer", "sandwich", "lmtest",
  "marginaleffects", "modelsummary", "knitr", "kableExtra",
  "ggplot2", "hexbin",
  "manifestoR"
))
```
