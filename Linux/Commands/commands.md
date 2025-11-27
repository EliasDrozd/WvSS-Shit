# Basic Linux Commands

## Updating & Upgrading your Linux Host

```
root@server ~#: apt update && apt upgrade -y
```

> ℹ️ **Info**
> It is required to be at least a root or sudo User in order to execute System Commands!

## Switching User Context

```
user@server ~#: sudo su
```

or

```
user@server ~#: sudo -i
```

## Updating & Upgrading complete packages

```
root@server ~#: apt update && apt-dist upgrade 
```
> ℹ️ **Info**
> Note, that Upgrading your System does required additonal time, so it is not recommended to upgrade your System in an Assessment Situation!

# Processes, Details & More

## Listing current Procs, Ports and Nodes

It can be vital and very usefull to know and check wether a configured Service is using the correct Port, Protocol and User context.
To allow us such insight use:

```
root@server ~#: lsof -i -P
```

# Advanced Linux Commands

The following commands are not that often used in school but are always good to know or can come in handy at times of need.

## Filesystem, Disk Space & Co.

In order to List the current Filesystems and their type quickly, use the following command:

```
root@server ~#: lsbkl -f
```

> ℹ️ **Info**
> This Command will list you the type of the Filesystem with the corresponding UUID, used & free space aswell as the current Mountpoint.
> Mountpoints are important for error or bug handling.

If a mount is not correctly listed, or might be blocked by some process use the following command to display all currently available Mountpoints:

```
root@server ~#: findmnt
```

If you wish to receive further Filesystem Infos for a specific Filesystem, use the following command:

```
root@server ~#: tune2fs -l /dev/<your File System (for ex. SDA2)>
```

This will print vital Information about the Blocks, reserved Blocks, used Blocks, the Mountpoint and the current State of the Filesystem