*******************************
Boot, Reboot System
*******************************

Rebbot with Shutdown command::

    sudo shutdown -r now

Show with w who is logged in and how long the shutdown did take::

    w

    USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
    centos   pts/0    h081217048191.dy 03:22    3.00s  0.04s  0.01s w

    uptime
     03:31:54 up 4 days, 18:39,  1 user,  load average: 0,00, 0,01, 0,05

Completely power machine off::

    sudo shutdwon -h now
    
====================================================
Change system into different operating modes
====================================================

System V-Runlevels
==================

Most common used::

    0 -> shutdown
    1 -> Single-user-mode
    2 -> Multi-user-mode
    3 -> Multi-user-mode with networking
    4 -> Normally not defined
    5 -> like 3 and graphical
    6 -> reboot
 
See which level your are::

    runlevel

To change runlevel:

Shutdown machine::

    reboot -r now

Hold Shift while machine is rebooting.

Get into Grub 2 Menu and change it.
