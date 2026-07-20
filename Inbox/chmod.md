---
tags:
  - sh
---

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

|                            |                                           |
|:-------------------------- | ----------------------------------------- |
| `chmod 644 file.txt`       | Standard file permissions                 |
| `chmod 755 dir/`           | Standard executable directory permissions |
| `chmod u=rw,go=r file.txt` | Symbolic equivalent of `644`              |
| `chmod u=rwx,go=rx dir/`   | Symbolic equivalent of `755`              |
| `chmod +x script.sh`       | Make script executable                    |

## Recursive Changes
Apply permission updates to directory trees.

|                                             |                                              |
|:------------------------------------------- | -------------------------------------------- |
| `chmod -R 755 project/`                     | Recursively set mode for all entries         |
| `chmod -R u+rwX project/`                   | Add read/write and smart execute recursively |
| `find project -type f -exec chmod 644 {} +` | Set files to `644`                           |
| `find project -type d -exec chmod 755 {} +` | Set directories to `755`                     |
| `chmod -R g-w shared/`                      | Remove group write recursively               |

## Special Bits
Setuid, setgid, and sticky bit examples.

|                                  |                                        |
|:-------------------------------- | -------------------------------------- |
| `chmod 4755 /usr/local/bin/tool` | Setuid on executable                   |
| `chmod 2755 /srv/shared`         | Setgid on directory                    |
| `chmod 1777 /tmp/mytmp`          | Sticky bit on world-writable directory |
| `chmod u+s file`                 | Add setuid (symbolic)                  |
| `chmod g+s dir`                  | Add setgid (symbolic)                  |
| `chmod +t dir`                   | Add sticky bit (symbolic)              |

## Safe Patterns
Use these patterns to avoid unsafe permission changes.

|                                   |                              |
|:--------------------------------- | ---------------------------- |
| `chmod 600 ~/.ssh/id_ed25519`     | Secure SSH private key       |
| `chmod 700 ~/.ssh`                | Secure SSH directory         |
| `chmod 644 ~/.ssh/id_ed25519.pub` | Public key permissions       |
| `chmod 750 /var/www/app`          | Limit web root access        |
| `chmod 755 script.sh`             | Safer than `777` for scripts |

## Common Errors
Quick checks when permission changes do not work.

|                                           |                                                                             |
|:----------------------------------------- | --------------------------------------------------------------------------- |
| `Operation not permitted`                 | Check file ownership with `ls -l` and apply with the correct user or `sudo` |
| Permission still denied after `chmod`     | Parent directory may block access; check directory execute (`x`) bit        |
| Cannot `chmod` symlink target as expected | `chmod` applies to target file, not link metadata                           |
| Recursive mode broke app files            | Reset with separate file/dir modes using `find ... -type f/-type d`         |
| Changes revert on mounted share           | Filesystem mount options/ACL may override mode bits                         |