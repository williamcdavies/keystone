# comp_trend_of_esacci_lakes_over_smoke_season variants (A–D)

## Dictionary
| Letter | High smoke year(s)                                                                                     | Low smoke year(s)                                  | Season window comes from                       | File       |
|:------ |:------------------------------------------------------------------------------------------------------ |:-------------------------------------------------- |:---------------------------------------------- |:---------- |
| **A**  | Most recent year at or above the high threshold                                                        | Most recent year at or below the low threshold     | That single high year                          | `..._A.py` |
| **B**  | Most recent year at or above the high threshold                                                        | All years at or below the low threshold (averaged) | That single high year                          | `..._B.py` |
| **C**  | Year with the greatest count of distinct smoke start days (among years at or above the high threshold) | All years at or below the low threshold (averaged) | That single high year                          | `..._C.py` |
| **D**  | All years at or above the high threshold (averaged)                                                    | All years at or below the low threshold (averaged) | Median of start/end days across all high years | `..._D.py` |