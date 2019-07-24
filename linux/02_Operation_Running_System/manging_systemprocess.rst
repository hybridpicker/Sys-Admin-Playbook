******************************
Managing User & System Process
******************************

*******************
Getting an Overview
*******************
To get overview of process::

    sudo su

    top

    top - 05:19:58 up 5 days, 20:27,  1 user,  load average: 0,01, 0,03, 0,05
    Tasks:  94 total,   2 running,  92 sleeping,   0 stopped,   0 zombie
    %Cpu(s):  0,0 us,  0,3 sy,  0,0 ni, 99,7 id,  0,0 wa,  0,0 hi,  0,0 si,  0,0 st
    KiB Mem :  1013192 total,   100148 free,   122128 used,   790916 buff/cache
    KiB Swap:        0 total,        0 free,        0 used.   576252 avail Mem 
    
      PID USER      PR  NI    VIRT    RES    SHR S %CPU %MEM     TIME+ COMMAND               
        1 root      20   0   54320   6032   3556 S  0,0  0,6   0:38.90 systemd               
        2 root      20   0       0      0      0 S  0,0  0,0   0:00.05 kthreadd              
        3 root      20   0       0      0      0 S  0,0  0,0   0:01.91 ksoftirqd/0           
        5 root       0 -20       0      0      0 S  0,0  0,0   0:00.00 kworker/0:0H          
        7 root      rt   0       0      0      0 S  0,0  0,0   0:00.00 migration/0           
        8 root      20   0       0      0      0 S  0,0  0,0   0:00.00 rcu_bh                
        9 root      20   0       0      0      0 R  0,0  0,0   0:05.71 rcu_sched             
       10 root       0 -20       0      0      0 S  0,0  0,0   0:00.00 lru-add-drain         
       11 root      rt   0       0      0      0 S  0,0  0,0   0:02.71 watchdog/0            
       13 root      20   0       0      0      0 S  0,0  0,0   0:00.00 kdevtmpfs             
       14 root       0 -20       0      0      0 S  0,0  0,0   0:00.00 netns                 
       15 root      20   0       0      0      0 S  0,0  0,0   0:00.02 xenwatch           


    PID -> Process ID (always unique!)
    USER
    PR -> Priority (lowest 20 -> highest -20)
    CPU is used
    MEM is used

Htop
===============

Mostly preferd -> htop:

    yum -y install htop

Starting with simply::

    yum -y install htop

***********************
Seeing Active Processes
***********************

Command ps:
ps - report a snapshot of the current processes associate with current user::

    ps

    PID TTY          TIME CMD
    4556 pts/0    00:00:00 sudo
    4563 pts/0    00:00:00 su
    4564 pts/0    00:00:00 bash
    4810 pts/0    00:00:00 sudo
    4812 pts/0    00:00:00 su
    4813 pts/0    00:00:00 bash
    5380 pts/0    00:00:00 ps

ps aux for ALL processes:

    ps aux

Combine with grep::

    ps aux | grep postgres

    postgres  2296  0.0  0.9 235052  9508 ?        S    Jul18   0:06 /usr/bin/postgres -D /var/lib/pgsql/data -p 5432
    postgres  2297  0.0  0.1 194796  1572 ?        Ss   Jul18   0:00 postgres: logger process   
    postgres  2299  0.0  0.3 235152  3348 ?        Ss   Jul18   0:00 postgres: checkpointer process   
    postgres  2300  0.0  0.1 235052  1992 ?        Ss   Jul18   0:03 postgres: writer process   
    postgres  2301  0.0  0.1 235052  1724 ?        Ss   Jul18   0:04 postgres: wal writer process   
    postgres  2302  0.0  0.2 235900  3032 ?        Ss   Jul18   0:05 postgres: autovacuum launcher process   
    postgres  2303  0.0  0.1 194928  1764 ?        Ss   Jul18   0:06 postgres: stats collector process   
    root      5651  0.0  0.0 112728   988 pts/0    R+   05:32   0:00 grep --color=auto postgres
    

To stop process -> Use kill-Command with PID Number (like 731)::

    kill 731

Get only PIDS by searching with pgrep::

    pgrep postgres
    2296
    2297
    2299
    2300
    2301
    2302
    2303

Get a Tree of pgrep::

    ps acjf

     PPID   PID  PGID   SID TTY      TPGID STAT   UID   TIME COMMAND
     4524  4525  4525  4525 pts/0     6172 Ss    1001   0:00 bash
     4525  4556  4556  4525 pts/0     6172 S        0   0:00  \_ sudo
     4556  4563  4556  4525 pts/0     6172 S        0   0:00      \_ su
     4563  4564  4564  4525 pts/0     6172 S        0   0:00          \_ bash
     4564  4810  4810  4525 pts/0     6172 S        0   0:00              \_ sudo
     4810  4812  4810  4525 pts/0     6172 S        0   0:00                  \_ su
     4812  4813  4813  4525 pts/0     6172 S        0   0:00                      \_ bash
     4813  6172  6172  4525 pts/0     6172 R+       0   0:00                          \_ ps
    
See all Kill-Signals with kill -l::
    
     1) SIGHUP	 2) SIGINT	 3) SIGQUIT	 4) SIGILL	 5) SIGTRAP
      ...


Set Down lower priorities by changing nice-Levels::

    nice -n 20 /bin/bash

Or renice it with PID - Number::

    renice 10 4525 

Output::

    4525 (process ID) old priority 19 new priority 10
