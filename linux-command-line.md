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

Check which shell you are on ====>
```
echo $SHELL
```
The `echo` command prints the results on the screen <br>
The `$` symbol helps you specify an enviroment variable

<br>


### Basic Commands
- echo: Print on screen ====>
  ```echo Hi```

- ls: List files and folders or directories ====>
  ```ls```

- cd: Change directory, navigates to other directories in the system ====>
  ```cd my_dir1```

- pwd: Present Working Directory, prints the current directory that you are on ====>
  ```pwd```

- mkdir: Make Directory, creates a directory ====>
  ```mkdir new_directory```

- Multiple commands, be sure to seperate them with a semicolon ====> ```;```
  ```cd new_directory; mkdir www; pwd:```


### Commands - Directories
- Make Directory Hierarchy ====>
  ```mkdir -p /tmp/asia/india/bangalore```

- Remove Directory ====>
  ```rm -r /tmp/mu_dir```

- Cop Directory ====>
  ```cp -r my_dir /tmp/asia/india/bangalore```


### Commands - Files
- Create a new file (no contents) ====>
  ```touch new_file.txt```

- Add contents to a file ====>
  ```cat > new_file.txt```

- View contents of a file ====>
  ```cat new_file.txt```

- Copy a file ====>
  ```cp new_file.txt copy_file.txt```

- Move and rename a file ====>
  ```mv /etc/new_file.txt /tmp/```
  ```mv /etc/new_file.txt /etc/new_sample_file.txt```

- Remove a file ====>
  ```rm new_file.txt```
