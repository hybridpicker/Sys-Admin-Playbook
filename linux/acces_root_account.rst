=============================
Manage Access to Root-Account
=============================
Get User to sudoer-file::

    sudo visudo

Get user into this line::

 ...
 ## Allow root to run any commands anywhere·
 root» ALL=(ALL) » ALL
 user ALL=(ALL)  ALL

Adding user to groups
======================

Adding user to group wheel::

    usermod -a -G wheel user

Checking in which group user is::

    groups user
