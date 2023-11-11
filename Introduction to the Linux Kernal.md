## Linux Kernal

<b> What is the Linux Kernal? </b> Kernal is the major component of an operating system, and is the core interface between a computer's hardware and it's processes.

<br>

The Kernal is responsible for 4 major tasks
- Memory Management: Keeps track of how much memory is used to store what and where
- Process Management: Determines which processes can use the CPU when, and for how long.
- Device Drivers: Act as a mediator or interpreter between the hardware and processes.
- System calls and Security: Receives requests for service from the processes.

<br>

## Kernal Versions
Displays information ablut the Kernal
```
uname
```

Use the -r or -a flag to print the Kernal version
```
uname -a
```
```
uname -r
```
Result:
```
4.15.0-72-generic
```
- 4 = Kernal Version
- 15 = Major Version
- 0 = Minor Version
- 72 = Patch Release
- Generic = Distro Specific Info


## Kernal And User Space
- User Space
  - Application/Programs

- Kernal Space
  - Kernal
  - Device Drivers


## Working with Hardware
Tool used to display messages from an area of the kernal called the ring buffer
```
dmesg
```

The udevadm utility is a management tool for udev <br>
The udevadm info command queries the udev database for device information
```
udevadm info --query=path --name=/dev/sda5
```

The udevadm monitor command listens to the kernal uevents
```
udevadm monitor
```

The lspic command stands for list PCI. <br>
This command is used to display information ablut all PCI devices that are configured in the system. <br>

Examples of PCI devices:
- ethernet cards
- Raid Controllers
- Video Cards
- Wireless adapters that directly attach to PCI slots in the motherboard of the computer

PCI is an abbreviation for peripheral component interconnect.
```
lspci
```

The lsblk command lists information about block devices
```
lsblk
```

The lscpu command displays information about the CPU architecture
```
lscpu
```

The lsmem command can be used to list the available memory in the system
```
lsmem --summary
```

The free command shows the total versus used memory in the system <br>
Use the -m flag to display the result in MB <br>
Use the -k flag to display the result in KB <br>
Use the -g flag to display the result in GB
```
free -m
```
```
free -k
```
```
free -g
```
