# Eukaryotic genome assembly and annotation on Galaxy: workshop notes

Notes, settings and a results guide from a hands-on workshop on assembling and annotating a eukaryotic genome with Galaxy (usegalaxy.eu). The workshop was organised by RSG Argentina and taught by Seba Chelaliche. [Check spelling and add date: ______]

This was my first time using Galaxy. I wrote this repository to keep the whole workflow in one place and to be able to repeat it on my own data. It is a learning record, not original research, and the numbers quoted from the demonstration are not my own results.

## Repository structure
```
galaxy-eukaryotic-genome-workflow-notes/
├── README.md
├── docs/
│   ├── workflow_steps.md
│   ├── concepts_and_metrics.md
│   └── troubleshooting.md
├── data/
│   └── README_data.md
├── results/
│   └── my_runs.md
├── screenshots/      
└── workflow/         
```

## What the workshop covered

| Step | Question it answers | Main tools |
|------|---------------------|------------|
| 1. Read quality control | Are the reads good enough to assemble? | FastQC, NanoPlot, MultiQC |
| 2. k-mer counting | How large and how repetitive is the genome? | Meryl, GenomeScope |
| 3. Trimming and filtering | Which reads or bases should go? | fastp |
| 4. Assembly | Can the reads be put back together? | Flye, Quast, Bandage |
| 5. Polishing | Can the draft be corrected using the reads? | Racon, Medaka |
| 6. Completeness | How many expected genes are present? | BUSCO |
| 7. Annotation (overview) | Where are the genes and what do they do? | Funannotate, InterProScan, EggNOG, genome browser |

The practical data were a 10% subsample of a Eucalyptus genome sequenced with Illumina (short reads) and Oxford Nanopore (long reads). Using both technologies is deliberate: long reads give contiguity, short reads give accuracy.

## What I ran myself and what I only watched

[Edit this section so it matches what you actually did.]

The public Galaxy server was slow during the session and several jobs were still queued when we moved on, so part of the output was inspected from the instructor's shared history. The annotation step was shown as a demonstration and was not run by participants.

- Ran myself: [for example, FastQC on the practice file, MultiQC, k-mer counting]
- Looked at in the instructor's history: [for example, Flye assembly, polishing, BUSCO]
- Only seen in the demo: annotation

Details are in results/my_runs.md.

## Repository contents

- docs/workflow_steps.md: the full procedure, step by step, with the settings used
- docs/concepts_and_metrics.md: short glossary, how to read the quality metrics, and the numbers shown in the demo
- docs/troubleshooting.md: problems we hit and how they were solved
- data/README_data.md: where the public practice datasets come from (no data stored here)
- results/my_runs.md: my own run log
- workflow/: workflows exported from my Galaxy account [add .ga files]
- screenshots/: figures from my own runs [add images]

## What I take from it

Reading the reports matters more than running the tools. The same FastQC warning means different things for a 16S amplicon file and for a genome, and trimming is a decision rather than a default: in this hybrid design the short reads were trimmed and the long reads were not. I also learned that BUSCO on a small subsample looks terrible by construction, so the number has to be read together with the data that produced it.

[Add one or two sentences in your own words about what was hardest.]

## What is still missing

My Galaxy skills are at a beginner level. I have not yet run the annotation step on my own, and I want to repeat the full workflow on a dataset of my own. I also want to reproduce the same steps on the command line.

## Credits

Workshop and practice material by RSG Argentina and the instructor. Datasets come from public Zenodo records listed in data/README_data.md. These notes are my own summary.
