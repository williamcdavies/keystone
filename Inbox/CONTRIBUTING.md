## Style Guide: Python
If anything is not explicitly documented under this style guide refer back to [PEP8](https://peps.python.org/pep-0008/).

### File Headers
File headers should be of the following format:

```python
"""
Filename: <filename>
Author: <author>
Modified: <date>
"""
```

The filename field should include the filename's extension. If the file belongs to a module, write the filename in endpoint format.

The author field should match the author field under `[project]` in `pyproject.toml`. 

The modified field should be of the format `DD/MM/YY`.

> [!example]
> 
```python
"""
Filename: <filename>
Author: <author>
Modified: <date>
"""
```


### General Format

#### Whitespace
There should be exactly one newline between the file header and the file content.

Every file should end in exactly one newline.