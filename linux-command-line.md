# Linux Command Line

### Linux OS
- Ubuntu
- Suse
- RHEL(paid) or Centos(free) - Both are the same OS
- Debian
- Kali

<br>

### Shell Types
- Bourne Shell (Sh Shell)
- C Shell (csh or tcsh)
- Z Shell (zsh)
- Bourne again Shell (bash)

<br>

Check which shell you are on 
```
echo $SHELL
```
The `echo` command prints the results on the screen <br>
The `$` symbol helps you specify an enviroment variable

<br>


### Basic Commands
- echo: Print on screen <br>
  ```echo Hi```

- ls: List files and folders or directories <br>
  ```ls```

- cd: Change directory, navigates to other directories in the system <br>
  ```cd my_dir1```

- pwd: Present Working Directory, prints the current directory that you are on <br>
  ```pwd```

- mkdir: Make Directory, creates a directory <br>
  ```mkdir new_directory```

- Multiple commands, be sure to seperate them with a semicolon  ```;``` <br>
  ```cd new_directory; mkdir www; pwd:```


### Commands - Directories
- Make Directory Hierarchy <br>
  ```mkdir -p /tmp/asia/india/bangalore```

- Remove Directory <br>
  ```rm -r /tmp/mu_dir```

- Cop Directory <br>
  ```cp -r my_dir /tmp/asia/india/bangalore```


### Commands - Files
- Create a new file (no contents) <br>
  ```touch new_file.txt```

- Add contents to a file <br>
  ```cat > new_file.txt```

- View contents of a file <br>
  ```cat new_file.txt```

- Copy a file <br>
  ```cp new_file.txt copy_file.txt```

- Move and rename a file <br>
  ```mv /etc/new_file.txt /tmp/``` <br>
  ```mv /etc/new_file.txt /etc/new_sample_file.txt```

- Remove a file <br>
  ```rm new_file.txt```


### User Accounts
- To know which user you are <br>
```whoami```

- Find information about the user <br>
  ```id```

- Switch from one user to another, this will prompt the user's password <br>
  ```su chaanyah```

- If you are accessing one system from another system using ssh, and you want to log into the other system using a different user <br>
  ```ssh chaanyah@192.168.1.2```

<br>

### Root User

```chaanyah``` is a regular user, so when this user trys to run the following command ```ls /root``` he will get a Permission denied message.

In order for user ```chaanyah``` to have access like root user, such installing and configuring software and services or viewing certain paths i.e the root directory, the root user will need to grant them sudo privileges by making an entry into the ```/etc/sudoers``` file

The user is still a regular user, but have root privileges
