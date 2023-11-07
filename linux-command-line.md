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
  ```
  echo Hi
  ```

- ls: List files and folders or directories <br>
  ```
  ls
  ```

- cd: Change directory, navigates to other directories in the system <br>
  ```
  cd my_dir1
  ```

- pwd: Present Working Directory, prints the current directory that you are on <br>
  ```
  pwd
  ```

- mkdir: Make Directory, creates a directory <br>
  ```
  mkdir new_directory
  ```

- Multiple commands, be sure to seperate them with a semicolon  ```;``` <br>
  ```
  cd new_directory; mkdir www; pwd:
  ```

<br>


### Commands - Directories
- Make Directory Hierarchy <br>
  ```mkdir -p /tmp/asia/india/bangalore```

- Remove Directory <br>
  ```rm -r /tmp/mu_dir```

- Copy Directory <br>
  ```cp -r my_dir /tmp/asia/india/bangalore```

<br>
  

### Commands - Files
- Create a new file (no contents) <br>
  ```
  touch new_file.txt
  ```

- Add contents to a file <br>
  ```
  cat > new_file.txt
  ```

- View contents of a file <br>
  ```
  cat new_file.txt
  ```

- Copy a file <br>
  ```
  cp new_file.txt copy_file.txt
  ```

- Move and rename a file <br>
  ```
  mv /etc/new_file.txt /tmp/
  ```

   <br>
   
  ```
  mv /etc/new_file.txt /etc/new_sample_file.txt
  ```

- Remove a file <br>
  ```
  rm new_file.txt
  ```

<br>
<hr>

### User Accounts
- To know which user you are <br>
```
whoami
```

- Find information about the user <br>
  ```
  id
  ```

- Switch from one user to another, this will prompt the user's password <br>
  ```
  su chaanyah
  ```

- If you are accessing one system from another system using ssh, and you want to log into the other system using a different user <br>
  ```
  ssh chaanyah@192.168.1.2
  ```

<br>

### Root User

```chaanyah``` is a regular user, so when this user trys to run the following command ```ls /root``` he will get a Permission denied message.

In order for user ```chaanyah``` to have access like root user, such installing and configuring software and services or viewing certain paths i.e the root directory, the root user will need to grant them sudo privileges by making an entry into the ```/etc/sudoers``` file

The user is still a regular user, but have root privileges

Once added onto the ```/etc/sudoers``` file, use the ```sudo``` prefix to gain access to sudo privileges. 
Example of sudo prefix with a command <br>

- ```
  sudo ls /root
  ```
- ```
  sudo ls /etc/sudoers
  ```
- ```
  sudo cat > /etc/bin/file.txt
  ```

Once the command is in the process of executing the command, the user will be asked for their password, after entering the password the command will be executed.

<br>

### Download Files
- The curl command along with the url of the file will download the file, and ```-O``` will save the result of the file, otherwise it will just print the file on screen <br>
  ```
  curl http://www.some-site.com/some-file.txt -O
  ```

- Another option is the wget command, -O to save the result of the file, then specify the name of the file that you want it to store locally as <br>
  ```
  wget http://www.some-site.com/some-file.txt -O some-file.txt
  ```

<br>

### Check OS Version
- Inspect the release files to know which version the OS that you are on <br>
  ```
  /etc/*relesase*
  ```
   <br>

  The release files may be named differently so use the asterisk wild card ```*```

- To check the details of the OS <br>
  ```
  cat /etc/*release*
  ```

<br>


## Package Managers

### RPM (Red Hat Package Manager)

- Install a package <br>
  ```rmp -i telnet.rpm```

- Uninstall a package <br>
  ```rmp -e telnet.rpm```

- Query a datanase and get details about the installed package <br>
  ```rpm -q telnet.rpm```

- Install a Package <br>
  ```yum install ansible``` 

- View a list of installed or available packages, provides the package name and version <br>
  ```yum list ansible```

- Remove an installed package
  ```yum remove ansible```

- List all available lists of a package that are duplicates
  ```yum --showduplicates l```

- Install a specific version of the package <br>
  ```yum install ansible-2.4.2.0```

<br>

### YUM

YUM installs all of the dependent packages for a certain service or software

- Install a package <br>
  ```yum install ansible```

- Information about the repository <br>
  ```/etc/yum.repos.d```

<br>

### YUM Repos
- To see a list of all repositories available on a system <br>
  ```yum repolist```

- Shows the files where these repositories are configured <br>
  ```ls /etc/yum.repos.d/```

- View the url of the location where all packages are stored <br>
  ```cat /etc/yum.repos.d/CentOS-Base.repo```

<br>

### Services
- Start a service in this case it will be HTTPD - Old Method <br>
  ```service HTTPD start```
  
- Start a service in this case it will be HTTPD - New Method (system cuttle command) <br>
  ```systemctl start httpd```

- Stop a running serive <br>
  ```systemctl stop httpd```

- Check the status of a service <br>
  ```systemctl status httpd```

- Configure a service to start automatically when the system boots up <br>
  ```systemctl enable httpd```

- Disable a service at boot up <br>
  ```systemctl disable httpd```

Example: You have a python program which is a simple web server that is developed in python, and the code is available at ```/opt/code/my_app.py``` run this server with the python interpreter ```/usr/bin/python3```, once it is running you can call the local host for port 5000 ```curl http://localhost:5000``` in this case it will return "Hello World" which is the response of the web server <br>

Run this server with the python interpreter along with the code <br>
```/usr/bin/python3 /opt/code/my_app.py```

Call that server
```curl http://localhost:5000```

The systemd services will allow the application to automatically start when the system boots up, it will also automatically restart when the system crashes <br>

Location of the unit files: <br>
```/etc/systemd/system```


- This command lets systemd know that there is a new service configured <br>
  ```systemctl daemon-reload```
