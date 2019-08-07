***************
LS Command
***************

'ls'-Command list files and folder that are in a directory::

    ls

-a shows All files (including hidden files) mostly with .filename -> . stands for hidden ::

    ls -a

Long listing shows more detail on items:

(permission, ownername, groupowner, size/bytes, month/day/year -> modified, Name)::

    ls -l

Sort list from size: Large -> Small with -Sl::

    ls -Sl

reverse that command with -r::

    ls -lrS

Note slice commands out is the same: -Sl = -S -l

List any specific directory with::

    ls -l <directory name>

or ::

    ls <directory name>

See al directory content and content in directory ls -R

Sort content with last modified file -t::

    ls -lt

Human readable -h  in combination with -l gives size output::
    
    ls -lh
