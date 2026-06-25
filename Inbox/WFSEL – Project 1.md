---
tags:
  - WFSEL
---
## Introduction

### Scope
The objective of this project is to produce, for each day in September 1992–December 2023, a dataset comprising mean, median, variance, minimum, and maximum values for each of the Lakes ECV in `['chla', 'tsm', 'acdom440', 'Kd490', 'KdPAR', 'phycocyanin', 'lake_surface_water_temperature', 'lake_surface_water_extent']` wherein each record corresponds to a single lake within the candidate set.

> [!note]
> This project depends upon data sourced from the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

### Candidate Set Selection
 Candidate lakes are identified by filtering the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file to retain only those records whose `country` field contains either `Canada` or `United States`:

```RBQL
SELECT * WHERE like(a4, '%United States%') || like(a4, '%Canada%')
```

The resulting candidate set comprises 667 North American lakes.

> [!note]
> Although the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file was published alongside the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/), its use extends to [Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

## Program Strategy

### Input
The program (`main.py`) takes four inputs:
1. `lakes_cci_merg_prod_nc_path`
2. `lakes_cci_stat_mask_nc_path`
3. `csv_path`
4. `dst_path`

> [!example]
> ```sh
> >>> python main.py ESACCI-LAKES-L3S-LK_PRODUCTS-MERGED-20230101-fv3.0.0.nc ESA_CCI_static_lake_mask.nc lakescci_v2.1.0_metadata_filtered ./ESACCI-LAKES-L3S-OUTPUT-20230101.csv
> ```