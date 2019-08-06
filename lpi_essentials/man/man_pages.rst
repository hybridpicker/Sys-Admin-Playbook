***************
Man pages
***************

Using command line to get help. man stands for Manual. Not written to be tutorials. Meant to be used as reference -> like dictionary. ::

    man ls

================
Manual Sections
================

Manual Pages are divided into 9 Sections:

    Section 1: Executable programs and shell commands 
    
    Section 2: System calls provided by the kernel
    
    Section 3: Library calls provided by program’s libraries 
    
    Section 4: Device files (usually stored in /dev)
    
    Section 5: File Formats
    
    Section 6: Games
    
    Section 7: Miscellaneous (macro packages, conventions, and so on
    
    Section 8: System administration commands (programs run mostly or
    exclusively by root)
    
    Section 9: Kernel routines

-> In the top left corner is always displayed in which section you are

To view section 5 -> for configuraition files::

    man 5 passwd


==============
Whatis Command
==============

List out summaries and realted man pages based on search term, invoked by entering::

    whatis <command>

Same result can you get with::

    man -f

================
Apropos Command
================

Comand that searches man page for appearances of the keyword provided invoked by entering::

    apropos <keyword>

Same result as ::

    man -k <keyword>

Apropos is very useful if you don't know how the command is spelled. It looks into commands and description of commands ::

    apropos search 

    ...
    find (1)             - search for files in a directory hierarchy
    ...
    lsearch (n)          - See if a list contains a particular element
    ...


Manual Page of man
==================

Manual itself has also a man-Page::

    man man

Search in the man pages for some keywords ::

    /<keyword>

And jump with 'n' to the next highlighted keyword.

