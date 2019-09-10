**************************
Shell Variables
**************************

To print out variables we need the dollar sign. For example with 'echo'::

    echo $VARIABLE 

    echo $PWD (Note same as 'pwd')
    -> /home/centos

OLDPWD Variable stores the path location where you were before you switched.

To see all variables of enviornment variables of currently logged in shell we can use 'env'-command ::

    env

To get that variables in alphabetical order we can use 'set'-command::

    set

Create Custom Variables
=======================

To create our own variable, we need to use the same Syntax. To create the variable TEST ::

    ~ $ TEST="testing"
    ~ $ echo $TEST
    testing

-> This creates a local variable. To get this variable executed for every shell we need to export this Variable with 'export'

    export TEST

To check that -> create a new Shell ::

    $ bash

and run the command::

    $ TEST

Real-World-Example
===================

A lot of third-party-programmers write software for linux that is run out of the /opt -directory.
To get the PATH-Environment to look through this directory we can modify this variable ::

    PATH=$PATH :/opt

-> $PATH is taking the current PATH environment variable to not loose it while storing this command
