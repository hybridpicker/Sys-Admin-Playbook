**************************************
Archives and Compression
**************************************

Archive compression is useful for saving space on our system.

================
tar-Command
================

Main command for doing this is 'tar'. Historically, tar was used for backup files and folders to backupsystems::

    tar <filename>.tar <directory_to_archive>

    tar backup.tar /home

Archives that are generated with tar is named as **tarballs**.

There are lots of necessary flags for this command::

    -c.......create a new archive
    
    -z.......pass the archive through gzip compression
    
    -j.......pass the archive through bzip2 compression
    
    -f.......file name of archive to create
    
    -x....... extract an archive
    
    -v.......verbose output

    -t ..... list tar contents

On example could be: Create a backup of /home called backup.tar  and store it into /media/backup ::

    tar -cvf /media/backup/home_backup.tar /home


GZIP vs BZP2
============

*GNU zip* (also known as GZIP) is a software application with the purpose to compress files. It was originally intended to replace the compress program used in the early Unix systems – to be used in the GNU Project (a free software project).

*BZIP2* is an open source lossless data compression algorithm – basically, a class of data compression algorithms that makes it possible for the original data of a compressed file to be completely reconstructed from the compressed data.

===========
zip-Command
===========

This command is creating a new compressed file ::

    zip archive.tar

If we also want zip to compress the files that are in the archive folder we can use -r ::

    zip -r

With the -r(recursively) flag, zip goes into every file in the archive and compress it.

===============
unzip-Command
===============

Extracting a zip archive. ::

    unzip archive.zip

===============
gzip-Command
===============

Creating a gizp archive ::

    gzip file2.txt

===============
gunzip-Command
===============

Exctract a gzip archive ::

    gunzip archive.gz

===============
bzip2-Command
===============

Creating a bizp archive ::

    bzip2 file.txt

===============
gunzip-Command
===============

Exctract a bzip archive ::

    bunzip2 archive.bvz2

======================
File Extensions
======================

File Extensions of archive files ::

    .tar.......tarball
    .zip.......zip archive
    .gz........gzip archive
    .bvz2.......bzip2 archive
