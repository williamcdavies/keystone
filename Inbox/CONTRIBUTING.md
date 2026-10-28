## Style Guide: Python
If something is not explicitly documented under this style guide refer to [PEP8](https://peps.python.org/pep-0008/).

### File Headers
File headers should be of the following format:

```python
"""
Filename: <filename>
Author: <author>
Modified: <date>
"""
```

The filename field should include the filename's extension. If the file belongs to a module, write the filename in endpoint format. The author field should match the author field under `[project]` in `pyproject.toml`. The modified field should be of the format `DD/MM/YY`.

> [!example]
> 
```python
"""
Filename: wfsel.exit_codes.py
Author: William Chuter-Davies
Modified: 17/10/26
"""
```

### Imports
Imports fall under the following three categories:
1. Standard Library Imports
2. Related Third-party Imports
3. Local Application/Library Specific Imports

These categories should be documented as follows:

```python

```


### General Format

#### Whitespace
There should be exactly one newline between the file header and the imports and exactly one newline following each import category.

Every file should end in exactly one newline.