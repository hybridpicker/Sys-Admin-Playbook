****************************************************
Verify the Integrity and Availability of resources
****************************************************

Resources generally mean:

-> Hard Drive Space

or

-> RAM

Check Hard Drive
=================

fsck -> FileSystemConcistencyChecker

1. List all block devices that are one the machine with lsblk::

    lsblk

    NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
    xvda    202:0    0   8G  0 disk 
    └─xvda1 202:1    0   8G  0 part /

2. Unmount device::

    sudo unmount /mnt -> unmoint device

3. Use FSCK for checking device::

    sudo fsck -y /dev/xvda1

Check RAM
=============== 

Memory Test -> Grub Menu (Shift while booting)

