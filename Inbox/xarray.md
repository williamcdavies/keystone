---
tags:
  - Personal
---

## Examples

### Read & Write netCDF Files

```python
>>> import xarray
>>> ds.to_netcdf(filename)
reopened = xr.open_dataset(filename)
reopened
```