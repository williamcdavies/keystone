## What is a Linux Package
A linux package is a compressed archive that contains all the file and metadata required to install and run a software application on a Linux system.

## Package Management Systems
Linux distributions use different package management systems to handle the installation, updating and removal of packages.
- **DEB (Debian Package)**: Ubuntu, Linux Mint, and Debian
	- Uses `.deb`
- **RPM (Red Hat Package Manager)**: Fedora, CentOS, RHEL (Red Hat Enterprise Linux)
	- Uses `.rpm

## Installing Packages

> [!note]
> 

### DEB
Use `dpkg`.

> [!example]

```sh
sudo dpgk -i example.deb
```

`dpkg` does not handle dependencies automatically. To install a package along with its dependencies use `apt`.

> [!example]

```sh
sudo apt install ./example.deb
```

### RPM
Use `rpm`.

> [!example]

```sh
sudo rpm -i example.rpm
```