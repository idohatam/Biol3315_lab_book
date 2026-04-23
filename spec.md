# Quarto Migration Spec (The Bluebook)

## Goal
Migrate the Biol 3315 Lab Manual from Bookdown to an HTML-only Quarto book, modernize renders (cross-references, LaTeX, phylogenetic trees), convert all `.Rmd` files to `.qmd`, update chunk options to `#|` syntax, and update the codebase.

## 1. Project Configuration (`_quarto.yml`)

The Quarto project will require a `_quarto.yml` file to handle the book structure:

```yaml
project:
  type: book
  output-dir: _book

book:
  title: "Biology 3315 Molecular Evolution and Phylogenetics"
  subtitle: "Lab manual"
  author: "Dr. Ido Hatam"
  cover-image: "cover_art_8.jpeg"
  chapters:
    - index.qmd
    - 01-lab1_intro_to_R_pt1.qmd
    - 02-lab2_intro_to_R_pt2.qmd
    - 03-lab3_biological_data1.qmd
    - 04-lab4_biologicaldata2.qmd
    - 05-lab5_pop_gen.qmd
    - 06-lab6_msa.qmd
    - 07-lab7_trees.qmd
    - 08-lab8_genome_trees.qmd

bibliography: [book.bib, packages.bib]

format:
  html:
    theme: cosmo
    toc: true
    toc-depth: 6
    number-sections: true
  pdf:
    documentclass: book
    keep-tex: true
```

## 2. File Index Mapping & Conversion
All target files will be renamed from `.Rmd` to `.qmd` during migration.

| Original Bookdown File | Target Quarto File | Reference 2025 File |
| :--- | :--- | :--- |
| `index.Rmd` | `index.qmd` | N/A |
| `01-lab1_intro_to_R_pt1.Rmd` | `01-lab1_intro_to_R_pt1.qmd` | `Biol_3315_lab1_2025.Rmd` |
| `02-lab2_intro_to_R_pt2.Rmd` | `02-lab2_intro_to_R_pt2.qmd` | `Biol_3315_lab2_2025.Rmd` |
| `03-lab3_biological_data1.Rmd` | `03-lab3_biological_data1.qmd` | `Biol_3315_lab3_2025.Rmd` |
| `04-lab4_biologicaldata2.Rmd` | `04-lab4_biologicaldata2.qmd` | `Biol_3315_lab4_2025.Rmd` |
| `05-lab5_pop_gen.Rmd` | `05-lab5_pop_gen.qmd` | `Biol_3315_lab5_2025.Rmd` |
| `06-lab6_msa.Rmd` | `06-lab6_msa.qmd` | `Biol_3315_lab6_2025.Rmd` |
| `07-lab7_trees.Rmd` | `07-lab7_trees.qmd` | `Biol_3315_lab7_2025.Rmd` |
| `08-lab8_genome_trees.Rmd` | `08-lab8_genome_trees.qmd` | `Biol_3315_lab8_2025.Rmd` |

## 3. General Editing Guardrails
- **File Extensions**: Convert all `.Rmd` files to `.qmd`.
- **Code Chunks**: Convert all R chunk options from the ` ```{r, option=value} ` syntax to the Quarto hashpipe ` #| option: value ` syntax.
- **Code Exercises**: DO NOT fix code chunks intended for students to solve. They must remain incomplete/broken.
- **Tone & Style**: Write in flowing academic prose. Do not use bold text for emphasis unless it already exists. Avoid adding bold titles to bullet points in explanatory text. Headers should only exist where they already exist in the reference files. The writing should read like a human instructor talking to students (pedagogical, rigorous but conversational, maintaining existing humor), not like an AI-generated document.
- **Dates**: Remove specific dates to keep the manual year-agnostic.
- **Tidyverse Syntax**: Use for data processing ONLY AFTER introduced in Lab 2.
- **Code breakdown**: Split large multi-step code chunks and explain step-by-step.
- **Deprecations**: Ensure no obsolete packages (e.g., old versions of 'ape'/'phangorn') are used. Correct the instructor if suggested.

## 4. Special Lab Content Mandates
- **Lab 7**: Introduce a brief tutorial for `ggtree` covering tree plotting and basic annotation. Ensure students use `ggtree` for visualization.
- **Lab 8**: Ensure students use `ggtree` for all phylogenetic tree visualizations.
