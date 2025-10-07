# Assessment 4 — Comparative Analysis of *Helicobacter anseris* (GCA_003364335)

**Student ID:** `asrauf`  
**Deliverables:** R Markdown report (code + narrative) and this public GitHub repository.

## Repo Structure
```
.
├── Assessment4_asrauf.Rmd          # Main R Markdown report (submit this)
├── Assessment4_asrauf.html         # Knit HTML (artifact)
├── Assessment4_asrauf.pdf          # Knit PDF (artifact)
├── data/
│   └── README.md                   # Put input files here: gene_expression.tsv, growth_data.csv
├── scripts/
│   └── render.R                    # Helper script to knit
├── .gitignore
├── LICENSE
└── CITATION.cff
```

## How to Reproduce
1. Ensure R ≥ 4.2 is installed.
2. Install required packages:
   ```r
   pkgs <- c("readr","dplyr","ggplot2","tidyr","Biostrings","seqinr")
   to_install <- setdiff(pkgs, rownames(installed.packages()))
   if (length(to_install)) install.packages(to_install)
   ```
   > *Biostrings* is from Bioconductor. If needed:
   ```r
   if (!requireNamespace("BiocManager", quietly=TRUE)) install.packages("BiocManager")
   BiocManager::install("Biostrings")
   ```
3. Add the two input data files to `data/`:
   - `gene_expression.tsv`
   - `growth_data.csv`
4. (Optional) Download CDS FASTA for *E. coli* and *H. anseris* via NCBI and update file paths in Part 2.
5. Knit the report:
   ```r
   rmarkdown::render("Assessment4_asrauf.Rmd", output_format = "html_document")
   # For PDF (requires LaTeX):
   # rmarkdown::render("Assessment4_asrauf.Rmd", output_format = "pdf_document")
   ```

## Notes for Markers
- The Rmd includes code chunks and written interpretation that align with the rubric (import/wrangle/visualise/infer; sequence metrics, codon usage, k-mers).
- External datasets (NCBI CDS FASTA) are referenced in comments to keep the repo lightweight.
- `sessionInfo()` can be printed at the end of the Rmd for environment provenance.

## License
See `LICENSE` (MIT) for code. Cite third-party data/tools per their terms.
