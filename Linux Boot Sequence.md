## Linux Boot Sequence Overview
The boot process can be broken down into 4 stages
- Stage 1: BIOS POST
- Stage 2: Boot Loader or GRUB2
- Stage 3: Kernal Initialization
- Stage 4: Service Initialization using sytemd or the INIT process


### Quick note on how to initiate a Linux Boot Process

Note: This can be achieved in one of two ways. <br>

The first method is to start a Linux device, which is in a halted or stopped state. <br>
The second method is to reboot or reset the running system.

- BIOS POST: Has very little to do with LInux itself
  - POST stands for power-on self-test
  - In this stage BIOS runs a POST to ensure that the hardware components attached to the device are functiong correctly.
  - If POST fails the computer may not be operable, and the system will not proceed to the second stage of the boot process.
- Boot Loader or GRUB2: Provides the user with the boot screen often with multiple options to boot into, such as Microsoft Windows OS or an Ubuntu 18.04 OS in an example of a dual boot system.
  - Once the selection is made in the boot screen, the boot loader loads the kernal into memory, supplies it with some permeters, and hands over the control to the kernal.
  - A popular example of the boot loader is the GRUB2, which stands for Grand Unified Bootloader version 2
  - GRUB2 is the primary boot loader for most current Linux distributions.
- Kernal Initialization: After the kernal is loaded into the memory, it is usually decompressed, this is done as the kernals are generally in a compressed state to save space.
  - The kernal is then loaded into the memory and starts executing, during this space the kernal carries out tasks such as initializing hardware and memory management tasks among other things.
  - Once it is completely operational, the kernal looks for an init process to run, which sets up the user space and the processes needed for the user environment.
- INIT Process: In most current day Linux distributions, the INIT function then calls the systemd daemon.
  - The systemd is responsible for bringing the Linux host to a usable state.
  - Systemd is also responsible for mounting file systems, starting and managing system services.
 
<br>

To check the init system
```
ls -l /sbin/init
```


## System Targets

To see the operation mode set in the system <br>
Dave's System:
```
runlevel
```
Results:
```
N    3
```

<br>

Bob's System:
```
runlevel
```
Results:
```
N    5
```

<br>

The operation mode that provides the graphical interface is called the run level 5. <br>
The operation mode that provides the non-graphical interface is called the run level 3. <br><br>

During boot, the init process checks the run level, it makes sure that all programs needed to get the system operational in that mode are started. <br>

For example, the graphical user mode requires a display manager service to run fo the GUI to work.


## Viewing and Changing Systemd Target
To see the default target
```
systemctl get-default
```

<br>

The above command looks up the file that is located at:
```
ls -ltr /etc/systemd/system/default.target
```

<br>

To change the default target
```
systemctl set-default multi-user.target
```


## File Types

There are 3 types of files:
- Regular File
- Directory
- Special Files

Regular files are the most common type of files that contains some text, data or images.
Examples:
- Configurations files
- Shell Scripts or code
- JPG files

<br>

Directory is a type of file as well that stores other files and directories within.
Example: The home directory
```
/home/username
```

<br>

Special Files can be subcategorized into five other file types
- Character Files: Repersents devices under the /dev file system, which allows the OS to communicate to IO devices serially.
- Block Files: Repersents block devices also located in /dev.
- Links: Associates two or more file names to the same set of file data, there are two types of links:
  - Hard Links: Associates two or more file names that share the same block of data on the physical disk.
  - Soft Links: Act as pointers to another file, deleting a symlink does not affect the data in the actual file.
- Sockets Files: Enables the communication between two processes.
- Named Pips: Allows connecting one process as an input to another.

<br>

## Making good use of the File Types In Linux
Running the command file with the file or directory name displays the file type
```
file /home/michael
```
```
file bash-script.sh
```
```
file insync1000.sock
```
```
file /home/michael/bash-script
```


## Filesystem Hierarchy
Contains the home directories for all users except for the root user
```
/home
```

<br>

The root user's home directory is located at /root
```
/root
```

<br>


If you want to install any third-party programs place them in the following file system
```
/opt
```

<br>


Used to mount file systems temporarily in the system
```
/mnt
```


<br>


Used to store temporary data
```
/tmp
```


<br>


All external media is mounted under the following file system
```
/media
```


<br>


df or disk file system prints out details about all of the mounted file systems.
```
df -hP
```


<br>


Contains the special block and character device files.
```
/dev
```
