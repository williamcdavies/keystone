---
tags:
  - CS447
---
Bash (short for "Bourne Again SHell") is an interactive command interpreter and scripting language developed for Unix-like [[Operating systems]]. Created in 1989 by Brian Fox for the GNU project, it is designed as a completely free software alternative for the Bourne shell, sh, and other propriety Unix shells, supported by the Free Software Foundation.

## Configuration and Dotfiles

| File                  | Scope       | Login Shells | Non-login Shells | Primary Use Case                                |
|:--------------------- |:----------- |:------------ |:---------------- |:----------------------------------------------- |
| `/etc/profile`        | System-wide | Yes          | No               | Global environment variables (`$PATH`, `etc.`)  |
| `/etc/bash.bashrc`    | System-wide | No           | Yes              | Global aliases/UI settings (Debian/Ubuntu)      |
| `/etc/profile.d/*.sh` | System-wide | Yes          | No*              | Modular scripts for specific packages           |
| `~/.bash_profile`     | User-only   | Yes          | No               | User-specific startup (often calls `~/.bashrc`) |
| `~/.bashrc`           | User-only   | No           | Yes              | User-specific aliases, prompts, and functions   | 
