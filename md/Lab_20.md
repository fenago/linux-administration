
Everyone Needs Disk Space

In this lab, you will learn how to manage your hard disk in Linux.
You will learn how to create new partitions on your drive. Then you will
learn how to create and mount filesystems. Finally, you will learn how
to use LVM to create logical volumes.


Where are your devices?
=======================

A file represents everything in Linux, and
devices are no exception. All your devices are located inside the
[/dev] directory; this includes your keyboard, mouse, terminal,
hard disk, USB devices, CD-ROM, and so on.

If you run the [w] command, you will see the name of the list of devices:

``` 
root@ubuntu-linux:~$ w
```

**Note:** You will get empty list since you are connected with virtual lab environment.

Where is your hard disk?
========================


To know which file represents your hard disk; you need to run the
command [lsblk], which is short for **list block**:

``` 
root@ubuntu-linux:~$ lsblk
```


So from the output of the [lsblk] command, you can conclude that we
only have one disk ([vda]) on my virtual machine.
