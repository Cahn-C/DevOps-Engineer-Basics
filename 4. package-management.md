## Introduction to Package Managers

### Package Managers
dpkg - Ubuntu <br>
apt - debian <br>
rpm - RHEL, CentOS, Fedora

<br>

### .deb
- Ubuntu
- Debian
- Linux Mint


### .rpm
- RHEL
- Centos
- Fedora

<br>
<br>

## Working with RPM

Install a package
```
rpm -ivh telnet.rpm
```

- -i stands for install
- -v stands for verbose (prints the detailed output of the command)
- -h stands for hash (prints 50 hash marks as the package archive is unpacked)


<br>

Uninstall a package
```
rpm -e telnet.rpm
```

<br>

Upgrade an existing package to a newer version
```
rpm -Uvh telnet.rpm
```

<br>

Query the database and get details about an installed package
```
rpm -q telnet.rpm
```

<br>

Verify a package
```
rpm -Vf <path to file>
```

<br>

## YUM Package Manager

YUM stands for Yellowdog Updater Modified

<br>

The reposiftory information is stored in the following file
```
/etc/yum.repos.d
```

<br>

Install software along with its dependencies
```
yum install httpd
```

<br>

Update a single package
```
yum update telnet
```

<br>

Update all packages in the system
```
yum update
```

<br>

Remove a package
```
yum remove httpd
```

<br>

Shows all repos added to your system
```
yum repolist
```

<br>

Check which package should be installed for a specific command to work
```
yum provides <command name>
```

<br>
<br>

## Working with DPKG

Install or Update an existing package
```
dpkg -i telnet.deb
```

<br>

Uninstall a package
```
dpkg -r telnet.deb
```

<br>

List packages installed in the system along with the version number and short description
```
dpkg -l telnet
```

<br>

Check the status of the package
```
dpkg -s telnet
```

<br>

Display details about packages such as version number, maintainer etc
```
dpkg -p <path to file>
```

<br>

## APT / APT-GET

APT stands for advanced package managers

<br>

Install software along with its dependencies
```
apt install gimp
```
```
apt-get install gimp
```

<br>

Software Repository
```
/etc/apt/sources.list
```

<br>

Refresh the repository
```
apt update
```

- A good time to run this would be immediately after installing the OS or after adding new sources

<br>

Install available upgrades of all packages currently installed on the system from the sources configured.
```
apt upgrade
```

<br>

Another way to update the repositories is using a text editor such as vim or nano
```
apt edit-sources
```

- This will open the /etc/apt/sources.list file
