***************
Analyzing Text
***************

=====================
Output to New File
=====================

To handle **stdout** (named as standartoutput)

>
===

'>' puts the output into a new file::

    head -n 1 plato.txt > heading.txt

IMPORTANT: Will always delete other input of heading.txt -> If already exists. To append output we can use '>>':

>>
===

'>>' puts output below existing data::

    head -n 1 aristoteles.txt >> heading.txt

============
cut-Command
============

Remove text from file and print specified fields to screen. ::

-d.........specifies delimiter to use
-f.........specifies which field to print

Example:

If we have this output::

    gutenberg $ cat heading.txt
    Project Gutenberg's Cicero's Tusculan Disputations, by Marcus Tullius Cicero
    Project Gutenberg's Book of The Republic of Plato, by Plato

We just want to get the Title we can tell cut to take every space (" ") as delimiter and count the fields we don't want (1:"Project", 2:"Gutenberg's") -> So we start from Field 3 to the last line. Our command have to look this way::

    $ cut -d" " -f 3- heading.txt
    Cicero's Tusculan Disputations, by Marcus Tullius Cicero
    Book of The Republic of Plato, by Plato

If we just want field 3 to 5 it looks like this ::

    $ cut -d" " -f 3-5 heading.txt
    Cicero's Tusculan Disputations,
    Book of The

Simple output this work into a new file ::

    cut -d " " -f 3-  heading.txt > works.txt

==============
sort-Command
==============

To sort lines in alphabetical order we can use **sort** ::

    $ cat works.txt
    Cicero's Tusculan Disputations, by Marcus Tullius Cicero
    Book of The Republic of Plato, by Plato

    $ sort works.txt
    Book of The Republic of Plato, by Plato
    Cicero's Tusculan Disputations, by Marcus Tullius Cicero

-n sorts the content numerically ::

    sort -n works.txt

============
wc count
============

This command prints number of lines, words and characters in file ::

     $ wc cicero_disputations.txt
      18516  184667 1069397 cicero_disputations.txt

If we just want the words to be counted we can use -w flag ::

    $ wc -w cicero_disputations.txt
    184667 cicero_disputations.txt

Same with lines(-l) and charcaters(-c) ::

    $ wc -l cicero_disputations.txt
    18516 cicero_disputations.txt

    wc -c cicero_disputations.txt
    1069397 cicero_disputations.txt

-> wc -wlc = wc

Practice Example ::

    $ echo "Words Lines" > sorting.txt
    $ wc -wl cicero_disputations.txt plato_republic.txt >> sorting.txt
    
    $ cat sorting.txt
    Words Lines
    18516  184667 cicero_disputations.txt
    29809  255816 plato_republic.txt
    48325  440483 insgesamt
