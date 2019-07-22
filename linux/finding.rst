Finding Files in Linux
======================

***************
File Names
***************

Searching for Files in the same directory::

    find -name test.txt

In the entire system::

    find / -name test.txt

Searching in directory etc::

    find /etc -name test.txt

Searchin without Casesensitiv::

    find /etc -iname test.txt

Find everythin that is NOT the file::

    find /etc -not -name test.txt
    find /etc -not -iname test.txt

Find every File that ends with log::

    ind / -type f -name "*.log"

***************
Data Size
***************

Find every file that is bigger than 2700Kb::

    find /usr/bin -size +27000c

Find every file that is bigger than 7Mb::

    find /usr/bin -size +7M

***************
Time Stemps
***************

Find all files that are created greater than one day ago::

    find /usr/bin -type f -mtime 1

Find all files that are created less than one day ago::

    find /usr/bin -type f -mtime -1

*************************
Ownership and Permissions
*************************

Find files that are owened by User Hybridpicker::

    find / -user hybridpicker

Find files that have permission from user hybridpicker::

    find /user/bin -perm 755

Find an exectute permission rewrite::

    find / .name "test.txt" -exec chmod 700 {} \;

***************
Locate Files
***************

Finding paths wit locate::

    locate test.txt

If not found use update DB::

    updatedb

***********************
Searching with Anchors
***********************

^ Is used as starting sign
$ is the end sign

Find Lines that starts with 'The'::

    grep '^The' alice.txt

Regular Expression for lowercase letters::

- Uppercase-Letter: [A-Z]
- Lowercase-Letters: [a-z]
- vowel: [aeiou]
- Numbers: [0-9]

So 'The' could also be searched like this::

    grep '^T[a-z][aeiou]' alice.txt

Search everything that ist not this letter::

    [^a]

Words Search
===============

Searching for words with space before and after like ' the '::

    --> \<  \>

Search every ' the '/' The ' now matter if starting word (-> No '^')::

    grep '\<[tT]he\>' alice.txt

Find every word that has to letters together::

    grep '\([a-z]\)\1' alice.txt
