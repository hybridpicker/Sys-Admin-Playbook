********************
Linux Users
********************

===============
who-command
===============

To check if any other is loggend in we can use the who-command::

    $ who
    centos   pts/0        2019-08-13 14:09 (h081217048191.dyn.cm.kabsi.at)
    
===========
w-command
===========

to get more detail about who is logged in we can use the w-command::

    $ w
     16:02:11 up 1 day, 22:02,  2 users,  load average: 0,00, 0,01, 0,05
    USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
    centos   pts/0    h081217048191.dy 14:09    3.00s  0.07s  0.01s w

-> Same Output with a few more deatils

This is a handy way for finding out if someone else is trying to enter the system.

===========
id-command
===========

Give us some infos about our user-account::

    $ id
    uid=1000(centos) gid=1000(centos) Gruppen=1000(centos),4(adm),10(wheel),190(systemd-journal) Kontext=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
    
    uid........Every account has a unique id on the system
    gid........Primary Group id that user accounts to
    groups.... List of every second group user is in

    wheel-group.... regular user accounts with special priveleges
