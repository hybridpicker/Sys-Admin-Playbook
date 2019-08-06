**********************
Locate, Find, Whereis
**********************

===============
Locate Command
===============

Searches a **local database** of files and folder looking for items that match the search-cirteria. ::

    locate passwd

-> Returns lot of output

===============
Find Command
===============

Find searches the **file system** (-> Find is a bit slower) for files that match the search criteria ::

    find /home/user/.config -name '*.xml'

This command searches for every Xml-file in the config-directory

==============
Whereis
==============

Locates binary, source and/or manual pages for a command ::

    ~ $ whereis cd
    cd: /usr/bin/cd /usr/share/man/man1/cd.1.gz /usr/share/man/mann/cd.n.gz
