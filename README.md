# Review Data Package v2

This package contains only synthetic generated-paper examples whose matching extracted-table JSON files contain at least one extracted table. The package is organized for anonymous review-time inspection in a Git repository.

## Inclusion rule

- start from each generator directory
- keep only `generated_paper_<id>` items where `generated_paper_<id>_extracted_tables.json` parses to an object with a non-empty top-level `tables` list
- copy the paired full paper source and extracted tables into a per-paper folder

## Included generators

- `gpt4o`: 976 retained papers, 2030 retained tables
- `gpt52`: 197 retained papers, 683 retained tables
- `qwen25_7b`: 351 retained papers, 488 retained tables
- `llama31_8b_instruct`: 237 retained papers, 466 retained tables

Total retained papers: `1761`
Total retained tables: `3667`

## Layout

- `MANIFEST.csv`: one row per retained paper
- `SUMMARY.csv`: generator-level summary with retention counts
- `<generator>/<paper_id>/paper.tex`: generated paper source
- `<generator>/<paper_id>/extracted_tables.json`: matching extracted tables

## Notes for reviewers

- all items here are synthetic generated papers, not human papers
- filenames remain traceable to the original generation ids
- some original corpora contain malformed or zero-table extracted JSON files; those were excluded from this package on purpose
