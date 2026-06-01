---
tags:
  - WFEL
---
## Classes

### Dataset

#### Constructor

```python
__init__(self, filename, mode="r", clobber=True, diskless=False, persist=False, keepweakref=False, memory=None, encoding=None, parallel=False, comm=None, info=None, format='NETCDF4')
```

## Examples

### Creating/Opening/Closing a netCDF File

```python
>>> from netCDF4 import Dataset
>>> rootgrp = Dataset("file.nc", "w", format="NETCDF4")
>>> print(rootgrp.data_model)
NETCDF4
>>> rootgrp.close()
```

---
## References
[netCDF4 - Dataset](https://unidata.github.io/netcdf4-python/#netCDF4.Dataset)
