---
tags:
  - Python
---

## Examples

### Read & Write netCDF Files

```python
>>> filename = "example.nc"
>>> ds.to_netcdf(filename)
>>> reopened = xr.open_dataset(filename)
```