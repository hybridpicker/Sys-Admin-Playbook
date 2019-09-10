*******************************
Permissions
*******************************

List Permissions
================

List Files with permission with ls -la::

    drwxrwxr-x. 4 centos centos      70 22. Jul 11:35 .
    drwx------. 7 centos centos     218 22. Jul 05:05 ..  
    -rw-rw-r--. 1 centos dbadmin 737280 22. Jul 11:36 backup.tar
    drwx------. 2 centos dbadmin     71 22. Jul 05:05 find
    -rw-rw-r--. 1 centos centos      77 22. Jul 04:40 shopping.txt
    -r--r--r--. 1 centos dbadmin     77 22. Jul 04:45 text.txt

   
First Sign:
 
'd' -> Directory

'-' -> normal File

3 groups of:

r - Read

w - Write

x - Excecute

First 3 Sets are for User-Permision

Second 3 Sets are for Group-Permission

Last 3 Sets are for Everyone -> or World

Change Permissions:
===================

Giving the User the permission for writing (w), reading (r) and excuting to text.txt ::

    chmod u+rwx text.txt

Check with ls -la::

     -rwxr--r--. 1 centos dbadmin     77 22. Jul 04:45 text.txt

Now delete Permission for group (g) and everyone (o)::

    chmod g-rwx text.txt
    chmod o-rwx text.txt

Or in one command::

    chmod go-rwx test.txt

Giving everyone permissions with 'a'::

    chmod a-rwx text.txt

Binary Style
==================

4 -> Read

2 -> Write

1 -> Execute

Every Set has a number (-> total value)

Example:

User needs all Rights: 4(read) + 2(write) + 1(execute) = 7
Group want to read and write: 4(read) + 2(write) = 6
Everyone just have to read: 4(read) = 4

Which comes to the command::

    chomd 764 test.txt
