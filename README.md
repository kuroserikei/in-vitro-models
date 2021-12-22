#A collection of scripts to query DepMap data base

##Introduction

DepMap is a data base with information about human cell lines, mostly cultures of immortalized cancer cells,and data on those cell lines.  In oncology research, in vitro experiments are performed on those cell line, and the outcomes are compared with the data collected in DepMap.  For now, we want to create tables that for a cell line, a gene and a type of data show a value.


We have data files for mutations, copy number, mRNA expression, CRISPR effect, shRNA effect for genes and cell lines.

We want to create two types of tables:

For a set G of genes and set C of cell lines, rows for cell lines, columns for genes and “results” as entries.
For copy number, mRNA expression, CRISPR effect, shRNA effect the results are as in the original data files but abbreviated to 7 characters – higher precision is not needed
For mutations, counts of deleterious and non-deleterious mutations.  More informative stat would be loss-of-function and no-loss-of-function mutation, but that seems to require a different model for each gene.
For a set G of genes and set C of cell lines report selected info on all mutations.  That allows to work on the loss-of-function issue 

We mark “no data available” with “NA” entries.

This collection of scripts uses awk: efficiency is not necessary, results in 1-2 minutes rather than in seconds, awk is very stable.  The code should run both in  MacOS (always installed) and in Linux using gawk (easy to install).  However, for Linux, we need to check for the behavior of zcat.

