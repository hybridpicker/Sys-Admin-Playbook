***************
Globbing
***************

Means the process of using wildcard characters for expanding non-specific file names.

====
"*"
====

An asterisk (*) matches any characters ::

    $ ls *.jpg

    example001.jpg	example004.jpg	example007.jpg	example010.jpg	example013.jpg	example01.jpg  example04.jpg
    example002.jpg	example005.jpg	example008.jpg	example011.jpg	example014.jpg	example02.jpg  example1.jpg
    example003.jpg	example006.jpg	example009.jpg	example012.jpg	example015.jpg	example03.jpg  example2.jpg

===
"?"
===

Question mark stands for and digit in a filename::
    
    $ ls example??.jpg

    example01.jpg  example02.jpg  example03.jpg  example04.jpg
    
    $ ls example?.jpg

    example1.jpg  example2.jpg

=====
"[]"
=====

Brackets are used to search for characters in a file name -> case sensitiv::

    $ ls [Ee]xample01.jpg

    example01.jpg

-> Searches for Example01.jpg and example01.jpg

For any files that start with a low letter we can use [a-z] ::

    $ ls [a-z]xample*.jpg

    example001.jpg	example004.jpg	example007.jpg	example010.jpg	example013.jpg	example01.jpg  example04.jpg
    example002.jpg	example005.jpg	example008.jpg	example011.jpg	example014.jpg	example02.jpg  example1.jpg
    example003.jpg	example006.jpg	example009.jpg	example012.jpg	example015.jpg	example03.jpg  example2.jpg

-> For upper letters we use [A-Z]

To exclude characters we can use "^" (carrot). First I create another file name 'pic01.jpg' ::

    $ touch Pic01.jpg

Now, we can search for any file in this directory that doesn't start with an capital 'P' ::
    
    jpg $ ls [^P]*
    
    example001.jpg	example004.jpg	example007.jpg	example010.jpg	example013.jpg	example01.jpg  example04.jpg
    example002.jpg	example005.jpg	example008.jpg	example011.jpg	example014.jpg	example02.jpg  example1.jpg
    example003.jpg	example006.jpg	example009.jpg	example012.jpg	example015.jpg	example03.jpg  example2.jpg
    
For a range of numbers we can use '[0-9]' ::

    $ ls example0[1-3].jpg

    example01.jpg  example02.jpg  example03.jpg
