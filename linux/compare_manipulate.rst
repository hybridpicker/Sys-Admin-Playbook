===============================
Compare and Manipulate Commands
===============================

Show more or less with cat::

    cat shoopinglist | more
    cat shoppinglist | less

Show alphabetical files with cat::

    cat hardwarelist.txt | sort 

 Sort and get the output two other data.txt::

    cat hardwarelist.txt shoppinglist.txt | sort > data.txt

Fixing  curios spaces and format::

    fmt -u format.txt

Show Line Numbers::

    nl data.txt
