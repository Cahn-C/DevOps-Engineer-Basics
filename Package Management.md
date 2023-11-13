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


