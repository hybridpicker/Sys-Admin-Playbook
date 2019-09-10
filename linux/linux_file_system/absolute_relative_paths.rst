***************************
Absolute and relative Paths
***************************

A path is a unique location to a file or a folder in a file system of an OS.A path to a file is a combination of / and alpha-numeric characters.

Absolute Path-name
==================

An absolute path is defined as the specifying the location of a file or directory from the root directory(/).
To write an absolute path-name:

Start at the root directory ( / ) and work down.
Write a slash ( / ) after every directory name (last one is optional)
For Example::

    $cat abc.sql

will work only if the fie “abc.sql” exists in your current directory. However, if this file is not present in your working directory and is present somewhere else say in /home/kt , then this command will work only if you will use it like shown below::

    cat /home/kt/abc.sql

In the above example, if the first character of a pathname is /, the file’s location must be determined with respect to root. When you have more than one / in a pathname, for each such /, you have to descend one level in the file system like in the above kt is one level below home, and thus two levels below root.

Relative Path-Name
===================

Relative path

Relative path is defined as the path related to the present working directly(pwd). It starts at your current directory and never starts with a / .

To be more specific let’s take a look on the below figure in which if we are looking for photos then absolute path for it will be provided as /home/jono/photos but assuming that we are already present in jono directory then the relative path for the same can be written as simple photos.

