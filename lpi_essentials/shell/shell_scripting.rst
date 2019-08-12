***************
Shell Scripting
***************
========
Shebang
========

Shebang is the first line in a bash script that tells bash what scripting language is being used.

Bash Files ::

     #!/bin/bash

Python ::

    #!/usr/bin/env python

========
Comments
========

Comments start with '#' ::

    #Comment Line

============
Permissions
============

In order to make every script to work we need to make it excecutable::

    chmod +x script.sh

=============
Execute File
=============

For executing File::

    $./script.sh

or absolute path::

    $/home/centos/scripts/script.sh


=============
If-Statements
=============

Basic If Statement::

    if [ something ]
    then
        do this
    fi

Basic If - Else Statement::

    if [ something ]
    then
        do this
    else
        do this
    fi

fi and ;;
=========

**fi** closes the if statement, while **;;** closes the current entry in the case statement.

======================
For loop - Statements
======================

Basic for loop setup::

    for variable in item1 item2 item3
    do
        command
    done

Examples
=========

For loop from 1 -> 10 ::

    for i in {1..10}
    do
      echo "$i"
    done

    Output:    
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10

Show every file in the DOCUMENTS-Folder::

   #!/bin/bash
  
   DOCUMENTS="/home/centos/docs"
   
   for doc in "$DOCUMENTS"/*
   do
     echo "$doc"
   done

Show every txt-File::

   #!/bin/bash
  
   DOCUMENTS="/home/centos/docs"
   
   for doc in "$DOCUMENTS"/*.txt
   do
     echo "$doc"
   done
