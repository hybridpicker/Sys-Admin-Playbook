========================
Process on Linux System
========================

What is  Process?

-> A Process is a set of instructions loaded into memory. These instructions come from a memory.

PID
====

Acronomy for Process ID.

===============
Init vs Systemd
===============

init
=====

When Computer starts in the past -> init

In Linux, init is a abbreviation for Initialization. The init is a daemon process which starts as soon as the computer starts and continue running till, it is shutdown. In-fact init is the first process that starts when a computer boots, making it the parent of all other running processes directly or indirectly and hence typically it is assigned “pid=1“.

systemd
========

A systemd is a System Management Daemon named with UNIX convention to add ‘d‘ at the end of daemon. So, that they can be easily recognized. Initially it was released under GNU General Public License, but now the releases are made under GNU Lesser General Public License. Similar to init, systemd is the parent of all other processes directly or indirectly and is the first process that starts at boot hence typically assigned a “pid=1“.

More Info about this topic: `The Story Behind Init and Systemd <https://www.tecmint.com/systemd-replaces-init-in-linux/>`_

PID1 -> First process

List the processes currently running on a system::

    ps

==============
Process Table
==============

This information includes general information about each process

- process id
- process owner
- process priority
- environment variables for each process
- the parent process
- pointers to the executable machine code of a process.

ps - Command
=============

If we just run *ps* -> We see processes running in our bash shell::

    ps

      PID TTY          TIME CMD
    10854 pts/0    00:00:00 sudo
    10856 pts/0    00:00:00 su
    10857 pts/0    00:00:00 bash
    10915 pts/0    00:00:00 ps

List proceses for a specific user -u::

    ps -u <username>

    ps -u hybridpicker
      PID TTY          TIME CMD
     4402 ?        00:00:03 uwsgi
     4404 ?        00:00:00 uwsgi
     4405 ?        00:00:00 uwsgi
     4406 ?        00:00:00 uwsgi
     4407 ?        00:00:00 uwsgi
     4408 ?        00:00:00 uwsgi
    ps -u centos
      PID TTY          TIME CMD
    10579 ?        00:00:00 sshd
    10580 pts/0    00:00:00 bash

To list all processes running on the system -e::

    ps -e

To also show the hierachy of process -H::

    ps -H
    
      PID TTY          TIME CMD
    10854 pts/0    00:00:00 sudo
    10856 pts/0    00:00:00   su
    10857 pts/0    00:00:00     bash
    10934 pts/0    00:00:00       ps

Can also be done with --forest::

    ps --forest
      PID TTY          TIME CMD
    10854 pts/0    00:00:00 sudo
    10856 pts/0    00:00:00  \_ su
    10857 pts/0    00:00:00      \_ bash
    10953 pts/0    00:00:00          \_ ps

Full format listing, including command arguments::

    ps -f

     ps -f
    UID        PID  PPID  C STIME TTY          TIME CMD
    root     10854 10580  0 05:07 pts/0    00:00:00 sudo su -
    root     10856 10854  0 05:07 pts/0    00:00:00 su -
    root     10857 10856  0 05:07 pts/0    00:00:00 -bash
    root     10962 10857  0 05:22 pts/0    00:00:00 ps -f

The ps -f Command gets that info from the /proc - directory. 

=================
Stopping Process
=================

First we need to find out the PID.

Then, in *top* -> press *k* then fille in <PID_NUMBER> -> press Enter

kill-Command
=============

simply type kill <PID> ::

    kill <PID>

    kill 3942


