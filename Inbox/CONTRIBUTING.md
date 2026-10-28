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

The filename field should include the file's extension. If the file belongs to a module, write the filename in endpoint format. The author field should match the author field under `[project]` in `pyproject.toml`. The modified field should be of the format `DD/MM/YY`.

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

These categories should be explicitly documented as follows:

```python
# Standard Library Imports

# Related Third-party Imports

# Local Application/Library Specific Imports
```

Imports should be ordered alphabetically within their category. Imports should be tab-aligned on the `import` keyword. Any successive imports should also be tab-aligned on the `import` keyword.

> [!example]

```python
# Standard Library Imports
import sys

from argparse import (

ArgumentParser,

Namespace,

)

  

# Related Third-party Imports

  

# Local Application/Library Specific Imports

from wfsel.exit_codes import (

EXIT_FAILURE,

EXIT_SUCCESS,

)

from wfsel.utils.argparse_utils import (

arguments_are_valid as _arguments_are_valid,

build_parser as _build_parser,

)
```


### General Format

#### Whitespace
There should be exactly one newline between the file header and the imports and exactly one newline following each import category.

Every file should end in exactly one newline.