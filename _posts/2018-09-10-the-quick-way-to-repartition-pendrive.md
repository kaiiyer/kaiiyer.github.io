---
layout: post
title: The quick way to repartition your pendrive  
---

If you are a distro hopper or your friend's go-to person for fixing computers, chances are you will end up writing bootable images to your pendrive multiple times per week. But how do you reinitialize the partition table of the pendrive once the rescue mission is over?

I know quite few of you reading this right now would want to shout "gparted". But what if I told you that there is a better way, a way to create parition table and format the drives according to your likes without touching GUI? Even better, what if I told you that, the utilities we are going to make use of today come shipped with default packages on most distributions?

Interested? read on

We are talking about two neat little utitlies, fdisk and mkfs which are shipped
as part of default packages in most of the linux distributions. Lets just not waste any more time. So here goes the guide...

First of all, just insert the pendrive onto your computer. Open up a terminal and type in the "dmesg" command. If you are on Debian, run the command with sudo. Hopefully, the command will output something like this:

    [67969.823527] sd 5:0:0:0: Attached scsi generic sg2 type 0
    [67969.824417] sd 5:0:0:0: [sdb] 7821312 512-byte logical blocks: (4.00 GB/3...
    [67969.825407] sd 5:0:0:0: [sdb] Write Protect is off
    [67969.825409] sd 5:0:0:0: [sdb] Mode Sense: 43 00 00 00
    [67969.825672] sd 5:0:0:0: [sdb] Write cache: disabled, read cache: enabled...
    [67969.839897]  sdb: sdb1
    [67969.840948] sd 5:0:0:0: [sdb] Attached SCSI removable disk

see the sdb written inside square brackets? that is your device file. On my computer, the newly connected pendrive is registered as /dev/sdb. On your system, it can be sdc or sdd depending on the number of secondary storage devices connected currently. I am going to continue using the "sdb" filename, but beware, it can be different on your system.

If you do a "ls /dev/sdb*" you will receive the following output

    /dev/sdb  /dev/sdb1 

The "/dev/sdb" is the pendrive and sdb1 is the partition on the pendrive. Please note that, your pendrive might have more than one parition, and it will be named sdb2, sdb3 etc. When you plug in a removable storage, most distributions make sure they get automatically mounted. Before continuing, we have to make sure the said partitions are not mounted.

We can use the "umount" command. Using umount, unmount each parition on the pendrive. Here I have only one partition, so a single command does the job for me.

    sudo umount /dev/sdb1

Now type in "sudo fdisk /dev/sdb" to launch the fdisk utility. Note that, here I am using the path to the whole device and not a partition.

    sudo fdisk /dev/sdb

after typing in the password, you will get the following screen 

    Welcome to fdisk (util-linux 2.32.1).
    Changes will remain in memory only, until you decide to write them.
    Be careful before using the write command.


    Command (m for help): 

Let us first create a DOS partition table on our pendrive. You can do this by typing in the "o" key and pressing enter.

    Command (m for help): o
    Created a new DOS disklabel with disk identifier 0xa191b1c8.

    Command (m for help):

Now we have a partition table which can be store information about the partition we are about to create. A new partition can be created by typing n and pressing enter

    Command (m for help): n
    Partition type
       p   primary (0 primary, 0 extended, 4 free)
       e   extended (container for logical partitions)
    Select (default p):

It now asks you to select between primary and extended partitions. These two types of partitions arose from the early limitations of PC partitioning schemes. To know more, visit this [link](https://www.tldp.org/LDP/sag/html/partitions.html)

For now, we can safely continue with primary parition by pressing enter. Once that is done, it will show a screen similar to the one shown below. Here, we will go with the default parition number (ie. 1) by pressing enter

    Using default response p.
    Partition number (1-4, default 1):

Once that is done, the system will ask you to select the first sector for our partition. The story repeats here (we are going to simply press enter)

    First sector (2048-15237119, default 2048):

Now comes the question of last sector. We are going to need a partition that is the size of our entire drive right? So we can press enter for this one too.

    Last sector, +sectors or +size{K,M,G,T,P} (2048-15237119, default 15237119):

And then, fdisk will finally bless you with a partition that spans the whole size of the drive.

    Created a new partition 1 of type 'Linux' and of size 7.3 GiB.
    
    Command (m for help):

So, we have a brand new parition right? mmm... not quite. We have to write it to the disk first. This can be done by typing "w" and pressing enter.

    Command (m for help): w
    The partition table has been altered.
    Calling ioctl() to re-read partition table.
    Syncing disks.

    [aswin@ThinkPad-L440 ~]$

And it will drop you back to the shell. Now we have a partition that spans our entire drive, but one without a file system. Let us now create the file system using the mkfs utility.

Type mkfs and double tap the Tab key. You will be greeted with a view similiar to the following.

    [aswin@ThinkPad-L440 ~]$ mkfs
    mkfs         mkfs.ext2    mkfs.ext4    mkfs.minix   mkfs.ntfs    mkfs.xfs
    mkfs.cramfs  mkfs.ext3    mkfs.fat     mkfs.msdos   mkfs.vfat

This shows all the partition types mkfs can create. Right now, let us create a FAT32 partition. This can be done as follows.

    [aswin@ThinkPad-L440 ~]$ sudo mkfs.fat /dev/sdb1 -n KARUVALLY
    [sudo] password for aswin:
    mkfs.fat 4.1 (2017-01-24)

As I have told already, replace sdb with the device name for your specific drive. The "-n" switch will apply the string that immediatly follows it as the name of the partition. Else, you will be stuck with a drive having a name of your favorite UNIX derivative.

If you want an NTFS drive, make sure to run the mkfs.ntfs command with the "-f" mode, or it will take an eternity, trying to fill your pendrive with zeroes. Also, note that mkfs.ntfs uses the "-L" switch to label the partition.

    [aswin@ThinkPad-L440 ~]$ sudo mkfs.ntfs /dev/sdb1 -f -L KARUVALLY
    Cluster size has been automatically set to 4096 bytes.
    Creating NTFS volume structures.
    mkntfs completed successfully. Have a nice day.

And there you have it. Your good old pendrive, ready to be used, at your service.
