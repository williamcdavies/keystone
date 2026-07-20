## Basic Syntax
Use these core command forms for `chmod`.

|                       |                         |
|:--------------------- |:----------------------- |
| `chmod MODE FILE`     | General chmod syntax    |
| `chmod 644 file.txt`  | Set numeric permissions |
| `chmod u+x script.sh` | Add execute for owner   |
| `chmod g-w file.txt`  | Remove write for group  |
| `chmod o=r file.txt`  | Set others to read-only |

## Numeric Modes
Common numeric permissions combinations.

|       |                                              |
|:----- |:-------------------------------------------- |
| `600` | Owner read/write                             |
| `644` | Owner read/write, group+others read          |
| `640` | Owner read/write, group read                 |
| `700` | Owner  full access only                      |
| `755` | Owner full access, group+others read/execute |
| `775` | Owner+group full access, others read/execute |
| `444` | Read-only for everyone                       |

## Symbolic Modes
Change specific permissions without replacing all bits.

|                    |                                    |
|:------------------ |:---------------------------------- |
| `chmod u+x file`   | Add execute for owner              |
| `chmod g-w file`   | Remove write for group             |
| `chmod o-rwx file` | Remove all permissions for others  |
| `chmod ug+rw file` | Add read/write for owner and group |
| `chmod a+r file`   | Add read for all users             |
| `chmod a-x file`   | Remove execute for all users       |

## Files and Directories
Typical permission patterns for files and directories