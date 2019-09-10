******************************
Pipes and Regular Expressions
******************************

=====================
grep-Command
=====================

grep show the lines in a file that match a given pattern ::

    grep <pattern> <file to search>
    
    $ grep republic plato_republic.txt
    had a myth respecting its own origin; the Platonic republic may also have
    
Normally grep is case sensitive. If we want a case-insensitive search we can use -i flag ::

    grep -i republic plato_republic.txt
    ......
    are not stated in the Republic; but in the VIIth Book of the Laws, where
    distorted by features adapted from the Republic. Whether this is the case
    End of the Project Gutenberg EBook of The Republic of Plato, by Plato
    ....

To get lines that do no contain the <pattern> we can use -v::

    grep -v republic plato_republic.txt


==================
Pipe character |
==================

Is used to send output of one command to another command. ::

    $ grep republic plato_republic.txt | less

To know how many charatcers are in the grep output::

    $ grep republic plato_republic.txt | wc -c
    75


====================
Regular Expressions
====================

Regular Expressions are great for precicser search::

    ^ .......Search the beginning of a line
    $ .......Search the end of a line
    . .......Stands in for a single character
    [abc] ...Search for other characters except for these
    * .......Match zero or more of the preceding characters or expression
