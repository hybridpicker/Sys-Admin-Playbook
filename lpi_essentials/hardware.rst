============
Hardware
============

Processor
=========

Core of the computer. Modern Processores have typically multiple cores. HAvin multiple processor cores that work independently can make the computer operate at higher speed.

The main companies for processores are:

- Intel
- AMD

CPU-Info-File
==============

We can find out infos about our processor by looking into the cpuinfo-File::

    cat /proc/cpuinfo

RAM
====

The processor stores data into RAM while working on it. View RAM statistics for the system::

    free

Show output in MB::

    free -m

Show output in GB::

    free -g

Motherboard
============

Part of the computer that connects everything together.

Show deatails about the motherboard, BIOS, processor and RAM on a system::

    dmidecode

Power Supply
=============

Brings power from wall socket to our motherboard. We have at least one. (Modern Computer have multiple power supplies.) Comes with different type of connectors with different voltage to get every powered like:

- Video-Cards
- Optical Devices
- Motherboard

etc..

Hard Drive
===========

Data is written in a consistent matter. So, if the computer is powerd off -> all data is stored in this drive. 

Hard Drives are often set up with **Partitions**.
-> 

All Hardrives are found under /dev - directory.

Next *sd* followed by a letter started with 'a'::

    /dev/sda
    /dev/sdb
    /dev/sdc
    ....

Partitions are named by a number in Linux. First Partition -> 1::

    /dev/sda1
    /dev/sda2
 
Hard drives are named block devices in Linux. We can list them with the lsblk-command::

    lsblk

View Free Space on a hard disk::

    df

also with hum readable format::

    df -h

Show statistics on the processor, RAM, and running processes::

    top

Optical Drives
==============

An optical drive is a type of computer disk drive that reads and writes data from optical disks through laser beaming technology.

This type of drive allows a user to retrieve, edit and delete the content from optical disks such as CDs, DVDs and Blu-ray disks. Optical drives are among the most common computer components.

An optical drive may also be known as an optical disk drive (ODD).
