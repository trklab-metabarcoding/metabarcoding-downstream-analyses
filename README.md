# metabarcoding-downstream-analyses
Downstream analyses after taxonomy assignment

[![DOI](https://zenodo.org/badge/1040975084.svg)](https://doi.org/10.5281/zenodo.17351279)

## Overview
This repository contains code for some common steps to prepare a phyloseq object—such as the one created in Step 4a/b of the trklab-metabarcoding obitools pipeline—for downstream analyses. Steps and their parameters listed should not be viewed as prescriptive; most are optional or customizable using different parameters based on the unique needs and goals of each project. These general steps, however, have become relatively standard steps in studies of herbivore diets in our lab, and should be considered before running major analyses (e.g., quantifying dietary richness or composition). 

## The steps included in this notebook are:
1. Read in phyloseq object (e.g., from step 4a/b of trklab-metabarcoding).
2. Filter to only samples of interest (e.g., a certain sample species, sequencing date, or collection type) if only a subset of samples will undergo major analysis. This is common in large projects. 
3. Remove (“prune”) any low-read samples. The code provided filters out samples <1,000 reads but this parameter can be changed to fit individual project needs.
4. Rarefy to even sequence read depth across samples. 
5. Save copies of phyloseq OTU table 1) before rarefying and 2) after rarefying. These .csv files should be viewed as the versions of record for any downstream analyses and carefully edited and formatted versions are commonly used as supplemental datasets in manuscripts. A few recent examples with supplementary datasets to reference for formatting: [Hoff et al. (2025) PNAS](#ref-hoff2025); [Littleford-Colquhoun et al. (2024) Royal Society Open Science](#ref-littleford2024). 
6. Merge phyloseq object with external data tables. This may occur if you want to add additional data on the taxa appearing in the taxonomy table, for example. 
7. Data summaries throughout. These summaries are often printed alongside a message describing that output for ease of reference and code annotation. 

## The final outputs of this notebook are:
1) A filtered pruned, and rarefied phyloseq object ready for downstream analyses.
2) Raw versions of OTU tables pre- and post-rarefaction to edit for inclusion in supplements to papers.
3) Data summaries that include metrics to report in papers. 

## References

### Source article:
<a id="ref-hoff2025"></a>
**Hoff et al. (2025)**: H.K. Hoff, B.L. Littleford-Colquhoun, R.Y. Kartzinel, H.M. Anderson, C. Geremia, L.M. McGarvey, C. Segal, & T.R. Kartzinel, The apportionment of dietary diversity in wildlife, *Proc. Natl. Acad. Sci. U.S.A.* **122** (29) e2502691122, https://doi.org/10.1073/pnas.2502691122 (2025).

### Source conceptual: 
<a id="ref-littleford2024"></a>
**Littleford-Colquhoun et al. (2024)**: Littleford-Colquhoun Bethan L., Geremia Chris, McGarvey Lauren M., Merkle Jerod A., Hoff Hannah K., Anderson Heidi, Segal Carlisle R., Kartzinel Rebecca Y., Maywar Ian J., Nantias Natalie, Moore Camela and Kartzinel Tyler R. Body size modulates the extent of seasonal diet switching by large mammalian herbivores in Yellowstone National Park, *R. Soc. Open Sci.* **11**:240136 http://doi.org/10.1098/rsos.240136 (2024).