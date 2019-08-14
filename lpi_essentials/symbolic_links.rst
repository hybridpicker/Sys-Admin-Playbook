***************
Symbolic Links
***************

Symbolic link is like a shortcut to another file.

We can do this with the ln-command and the -s (symbolic) flag::

    ln -s <path_to_file> <link_name.lnk>
    ln -s Documents/test.txt test.txt.lnk

If we change the the symbolic link -> original file gets also changed.

With ls -l w can see where the link is going to::

     $ ls -l
    insgesamt 4
    -rw-rw-r--. 1 centos centos 18 14. Aug 04:07 text.txt
    lrwxrwxrwx. 1 centos centos 10 14. Aug 04:08 text.txt.lnk -> ./text.txt

if color is RED -> means that link is broken.

===============
Break the link
===============

We cam remove the link from a file with the unlink command::

    unlink <link>
    unlink test.txt.lnk

    $ unlink text.txt.lnk
    text_files $ ls -l
    insgesamt 4
    -rw-rw-r--. 1 centos centos 18 14. Aug 04:07 text.txt
