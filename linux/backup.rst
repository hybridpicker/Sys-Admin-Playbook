==============
Back Up Files
==============
Make archive with tar form directory data with no compression::

    tar cvf databackup.tar ./data

List all files in backup.tar::

    tar tvf backup.tar 

Compress with gzip::

    gzip backup.tar

Compress and zip in one-way-command::

    tar cvfz databackup.tar.gz ./data

Decompress Files
================

Unpacking archive with x (-> extract)::

    tar xvfz databackup.tar.gz


