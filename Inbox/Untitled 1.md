# comp_trend_of_esacci_lakes_variable_over_smoke_season Strategies (A–D)

  

## Dictionary

| Strategy     | Window size | Selection strategy | High smoke year(s)                                        | Low smoke year(s)                                  | Season window comes from                       | File       |
|:------------ |:----------- |:------------------ |:--------------------------------------------------------- |:-------------------------------------------------- |:---------------------------------------------- |:---------- |
| **$A_{4E}$** | 4           | Earliest           | Most recent year at or above the high threshold           | Most recent year at or below the low threshold     | That single high year                          | `..._A.py` |
| **$A_{4L}$** | 4           | Latest             | Most recent year at or above the high threshold           | Most recent year at or below the low threshold     | That single high year                          | `..._A.py` |
| **$B_{4E}$** | 4           | Earliest           | Most recent year at or above the high threshold           | All years at or below the low threshold (averaged) | That single high year                          | `..._B.py` |
| **$B_{4L}$** | 4           | Latest             | Most recent year at or above the high threshold           | All years at or below the low threshold (averaged) | That single high year                          | `..._B.py` |
| **$C_{4E}$** | 4           | Earliest           | Year with the greatest count of distinct smoke start days | All years at or below the low threshold (averaged) | That single high year                          | `..._C.py` |
| **$C_{4L}$** | 4           | Latest             | Year with the greatest count of distinct smoke start days | All years at or below the low threshold (averaged) | That single high year                          | `..._C.py` |
| **$D_{4E}$** | 4           | Earliest           | All years at or above the high threshold (averaged)       | All years at or below the low threshold (averaged) | Median of start/end days across all high years | `..._D.py` |
| **$D_{4L}$** | 4           | Latest             | All years at or above the high threshold (averaged)       | All years at or below the low threshold (averaged) | Median of start/end days across all high years | `..._D.py` |