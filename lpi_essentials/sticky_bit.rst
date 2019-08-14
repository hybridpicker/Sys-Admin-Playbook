*****************************************
Special Files, Folders and the Sticky Bit
*****************************************

Files that **do not** get deleted on reboot are stored in /var/temp::

    ls /var/tmp

The /tmp folder contains temporary files that *do* get deleted on reboot::

    ls /tmp


Sticky Bit
==========

A sticky bit is a permission that only allows users that create their own files and folder can delete theirs and not another 'users'

with the ls -ld will show permission that are setup::

    $ ls -ld /tmp
    drwxrwxrwt. 9 root root 249 14. Aug 04:18 /tmp

    drwxrwxrwt....t is a sticky bit


Apply the sticky bit to a folder::

    chmod o+t /path/to/directory
    t.....Note for sticky bit
  

normally chmod need this format::

    chmod 0777

Technically we hide that 0 if not used. so chmod 0777 = chmod 777

1..... stands for sticky bit::

    chmod 1777 /path/to/directory
