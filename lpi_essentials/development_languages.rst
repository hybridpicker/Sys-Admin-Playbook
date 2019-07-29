======================
Development Langugages
======================

********************************
Open Source Software Development
********************************

Based on the book "The Cathedral & The Bazaar" -> 2 main models:

Cathedral Model
===============

- Restrictive
- Source Code released when software is released

Bazaar Model
============

- more open
- source code is always available via the web

Idea behind it: more programmers can optimize the code -> get better software

********************************
Development Language Catgeories
********************************

Compiled Languages
==================

- C
- C++

Scenario:
I've created a program on Machine A and want it to run on Machin B. After finishing:

Compiler goes through Source Code and creates a seperate File for Machine B (-> Machine Code 1,0,1,0,0,1) and gives that to the other machine to make it executable - directly - on this machine.

- Source Code of Machine A is never seen by Machine B

Pros:

- fast
- ready to run
- source code is private

Cons:

- not cross-plattform (If I compile it for Windows it won't work for Mac)
- inflexible
- extra step

Interpreted Languages
======================

- Python
- Java
- Perl
- PHP

Same Scenario:

Machine A gives B a copy of the source code. Machine B interprets the source code whenever it runs to program. Interpreter is different process than compiling. Interpreter does its work on the fly and does not save it. -> Best Example: JavaScript while browsing on WebPages.

Pros:

- cross-plattform
- simpler to test
- easier to debug

Cons:

- interpreted required
- often slower
- source code is public


Assembly Languages
==================

Wiki: `Assembly Languages <https://en.wikipedia.org/wiki/Assembly_language>`_
