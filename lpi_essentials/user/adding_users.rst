***************
Adding Users
***************

==============
Create  Group
==============

groupadd will create Group with GroupID::

    groupadd spicegirls

To see group_ID::

    cat /etc/group

====================
Create User Account
====================

To get our new user into our created secondary group::

    sudo useradd <username> -G 1003 -m -c <Full Name> <Username_for_logging_in>

    sudo useradd mel -G 1003 -m -c "Melanie C" mel

Note: -m is for creating homedirectory
-c is for the commentfield

The user add command gets behaviour instructions from /etc/default/useradd::

    $ cat /etc/default/useradd
    # useradd defaults file
    GROUP=100
    HOME=/home
    INACTIVE=-1
    EXPIRE=
    SHELL=/bin/bash
    SKEL=/etc/skel
    CREATE_MAIL_SPOOL=yes

/etc/skel has contents within this direcotry are copied into home directories of newly created users.

===============
Change Password
===============

With sudo-permissions we can user passwd-command to change the password of a user::

    sudo passwd mel

In the /etc/passwd - File we can see 'x' for password. This means that the password is encrypted::

    mel:x:1002:1003:Cloud User:/home/centos:/bin/bash

To get infos about encrypted passwords we can take a look into the /etc/shadow file::

    sudo cat /etc/shadow
    mel:$6$Gk.AnA$H/z/SkCJAfydx.L8i0FiNL3ERDWCbcPVJVU2U/zAD7WoKwwBmaFJ4G//vN88K1gFoFeIaF1:18100:0:99999:7:::

    <username>:<encrypted_pw>:<days since 01.01.1970 the pwd was last changed>:<number_of_days_a_user_will_have_to_change_pwd>:<maximum_pwd_age>:<pwd_warning_period>::

=============
last command
=============

To see which users are logged in the last time in chornological order::

    $ last

    last
    mel            pts/0        h081217048191.dy Wed Aug 14 03:30   still logged in   
    hybridpicker   pts/0        h081217048191.dy Tue Aug 13 18:37 - 21:12  (02:34)    
    centos         pts/0        h081217048191.dy Tue Aug 13 14:09 - 18:18  (04:08)    
    centos         pts/0        h081217048191.dy Tue Aug 13 10:05 - 12:20  (02:14)    
