==================
Package Management
==================

- Software for install software on a linux system

In Windows:

Application comes with own installers that place the software py itself

In Linux:

Already installed package manager takes files from Web - known as repository - and install it into the system.

Package manager checks it files that are need for programm are already installed on the system  - known as libary files. If not, it installs it to make prossible to install the wanted program. These files are named dependencies.

===========================
What Constitutes a Package?
===========================

Dependency Information
======================

- What other software is required to make that package work?

Version Information
===================

Architecture Information
==========================

- What type of CPU is this package model for?


=================
2 Ways to Install
=================

Overview of Installing Packages on Linux

Installing from Source
======================

- Install tar-Balls
- Slack
- Gentoo

=================
Prebuild Packages
=================

- RPM
- .dep

RPM -> Red Hat Package Manager
==============================

Denotated by .rpm File Extension

Used on following Institutions:

- Red Hat Enterprise Linux
- Fedora
- CentOS
- SUSE
- openSUSE

Packages are installed via command line or graphical tools:

- YUM (command line) - Red Hat Enterprise Linux, CentOS, Fedora
- ZYPPER (command line) - SUSE, open SUSE
- GNOME (graphical) - Red Hat Enterprise Linux, CentOS, Fedora
- YaST (graphical) - SUSE, openSUSE

Debian
==============================

Denotated by .dbe File Extension

Used on following Institutions:

- Debian
- Ubuntu
- Linux Mint
- Elementary OS

Packages are installed via command line or graphical tools:

- aptitude (command line)
- GNOME - Software (graphical)

=================
Software Updates
=================

Modern distribution checks periodically for updates:

- Notification will appear in a graphical -> Can approve updates
- CommandLine: User hast to initial-check
