# SearchCal Tables

This repository's purpose is to generate more useful tables from SearchCal output and output mediawiki-formatted tables for the Roman targets wiki.

## A quick tour:

### generating_settings.md

This file details the settings used in SearchCal to generate the initial .csv tables posted to the Roman wiki for the CHARA 2025A targets.

### searchcal_read.ipynb

This notebook (yes, it's hideous, I know) reads in the SearchCal .csv tables (found in the location specified by the variable `searchcal_out_table_dir`) and outputs three things (into the location specified by the variable `sifted_table_dir`). These are:
1. An .ecsv file containig the resulting table.
2. A .md file containing the resulting table in markdown format.
3. A .txt file containing the resulting table as a mediawiki-formatted table with some extra notes thrown in.

It also does a very rudamentary "scoring" of the calibrators, by default primarily based on their distance from the optimal locations for them to be (~30 minutes of RA ahead or behind the target, no DEC change). This scoring can be modified to your heart's content in the `CalibratorScore` function, the higher the score the better, and thus the calibrators are sorted in the output tables (the target star gets an infinite score so it ends up on top).

If you, for some unholy reason, wish to run this awful code... good luck and contact me with any questions.
