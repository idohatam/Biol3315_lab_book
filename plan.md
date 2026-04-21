# Quarto Migration and Update Plan

This plan details the step-by-step process for converting the Biol 3315 Lab Manual to an HTML-only Quarto book and updating the content of the 8 labs. 

Each phase includes validation via `quarto render` and a git commit upon successful completion.

### Phase 1: Quarto Base Setup
- [ ] 1. Create `_quarto.yml` according to `spec.md`.
- [ ] 2. Rename `index.Rmd` to `index.qmd`.
- [ ] 3. Update `index.qmd` (remove bookdown YAML, adjust formatting for Quarto books, ensure syntactical correctness).
- [ ] 4. Render the book with `quarto render` to ensure basic compilation.
- [ ] 5. Commit the Quarto skeleton.

### Phase 2: Sequential Lab Updates
For each lab below, the process will be:
1. Rename the original `0X-labX...Rmd` file to `.qmd`.
2. Read the corresponding `2025_reference/Biol_3315_labX_2025.Rmd` file.
3. Edit the `.qmd` file to:
   - Update content based on the reference file.
   - Convert all code chunk options to `#|` syntax.
   - Apply Quarto cross-referencing syntax.
   - Fix LaTeX math blocks.
   - Ensure pedagogy (preserve broken student code).
4. Test code chunks and run `quarto render`. Debug any failures.
5. Commit the changes to `dev`.

- [x] **Lab 1 Update (`01-lab1_intro_to_R_pt1.qmd`)**
  - Read `Biol_3315_lab1_2025.Rmd`
  - Update main lab file, convert to `.qmd`, update chunk options, remove dates, verify code blocks.
  - Render & Commit.

- [ ] **Lab 2 Update (`02-lab2_intro_to_R_pt2.qmd`)**
  - Read `Biol_3315_lab2_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Ensure Tidyverse is introduced here. Future labs can now use tidy syntax.
  - Render & Commit.

- [ ] **Lab 3 Update (`03-lab3_biological_data1.qmd`)**
  - Read `Biol_3315_lab3_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - Render & Commit.

- [ ] **Lab 4 Update (`04-lab4_biologicaldata2.qmd`)**
  - Read `Biol_3315_lab4_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - Render & Commit.

- [ ] **Lab 5 Update (`05-lab5_pop_gen.qmd`)**
  - Read `Biol_3315_lab5_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - Render & Commit.

- [ ] **Lab 6 Update (`06-lab6_msa.qmd`)**
  - Read `Biol_3315_lab6_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - Render & Commit.

- [ ] **Lab 7 Update (`07-lab7_trees.qmd`)**
  - Read `Biol_3315_lab7_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - **Special Mandate**: Add `ggtree` tutorial for tree plotting and annotation. Convert appropriate visualizations to use `ggtree`.
  - **Special Mandate**: Add `#| cache: true` to the maximum likelihood tree chunk with bootstrapping to avoid long render times.
  - Render & Commit.

- [ ] **Lab 8 Update (`08-lab8_genome_trees.qmd`)**
  - Read `Biol_3315_lab8_2025.Rmd`
  - Convert to `.qmd` and update chunk options.
  - Explicitly update content based on the 2025 reference file.
  - **Special Mandate**: Ensure tree plotting uses `ggtree`.
  - Render & Commit.

### Phase 3: Final Review
- [ ] 1. Perform a complete clean `quarto render` of the entire project.
- [ ] 2. Final check of output formatting (figures, math, tables).
- [ ] 3. Final commit and push of `dev` branch.
