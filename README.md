# LAPD Search Threshold Test

## Developed by the Stanford Open Policing Project (SOPP)

### 

In consultation with the Stanford Open Policing Project, a Los Angeles Times analysis found that LAPD officers search black and Latinos far more often than whites during traffic stops even though whites are more likely to be found with illegal items.

To report the story, we filed an open records request and obtained 10 months worth of traffic stop data collected by the LAPD under the California Racial and Identity Profiling Act, which went into effect last summer.

We used a statistical model — known as a threshold test — that combines data from search rates of each racial group and the rate at which those searches were successful in finding contraband. The model was developed by the Stanford Open Policing Project, which has analyzed traffic stop data at dozens of law enforcement agencies across the nation.

The analysis showed that officers had a lower standard of evidence when deciding to search Latino and black vehicle occupants. This was true, even when excluding non-discretionary searches as the primary reason for the police action. 

Such searches — conducted as condition of probation or parole, after an arrest was made, as part of a search warrant or during an inventory of an impounded vehicle — don’t capture whether officers demonstrate bias, experts said. Those "non-discretionary" searches can also lower the rates at which officers find contraband during searches.

We cloned the Stanford repository and ran our own analysis. We then later shared the LAPD data with Stanford data scientist Amy Shoemaker who was kind enough to run the LAPD through the threshold test model. She created a hierarchy filter to flag searches as discretionary or non-discretionary. The filter excludes stops where non-discretionary searches were the primary reason for the police action and categorizes those with multiple reasons for a search. So if a stop included both a consent search and a vehicle inventory search it was included in the analysis because a consent search is considered discretionary and given a higher rank in the hierarchy model. Shoemaker's findings for all searches and discretionary searches were consistent with our initial results, which showed lower search thresholds for non-whites.

## Required System Packages

### All Systems
* R

### Fedora
* gdal-devel
* proj-nad
* proj-epsg
* proj-devel
* v8-314-devel (libv8-3.14-dev ubuntu)
* libjpeg-turbo-devel

### Mac

## Getting Started
1. [command line] Clone the repository
```
git clone https://github.com/stanford-policylab/opp.git
```
2. [command line] Change directories
```
cd opp/lib
```
3. [command line] Start R
```
R
```
4. [R] install the required packages
```R
install.packages(c(
  "digest",
  "fs",
  "functional",
  "getopt",
  "glue",
  "here",
  "jsonlite",
  "knitr",
  "lubridate",
  "lutz",
  "maps",
  "purrr",
  "rgdal",
  "rlang",
  "rmarkdown",
  "rstan",
  "sp",
  "stringr",
  "suncalc",
  "tidyverse",
  "zoo"
))
```
5. [R] load the main library
```R
source("opp.R")
```
6. [R] download some clean data
```R
opp_download_clean_data("wa", "seattle")
```
7. [R] load the clean data
```R
d <- opp_load_clean_data("wa", "seattle")
```
