***************************
Viewing Text
***************************

less-Command
==================

viewing a text file with the ability to scroll through the pages of the file::

    less README

head-Command
==============

viewing the first ten line of a file::

    head README

We can specify how man lines we want to see with -n::

    head -n <number> README

    head -n 20 README

tail Command
=============

view the last ten lines of a file::

    tail README

also has a -n Flag for number of lines we want to see::

    tail -n<number> README

    tail -n30 README

To show last ten lines in realtime (like we want to see in log files as sysAdmins) we can use -f::

    tail -f /var/log/secure

-> Shows last ten lines in realtime

-> Good way to catch traffic
