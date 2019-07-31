******************
Package Management
******************

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

******************
Commands
******************

======================
YUM - Update - Command
======================

Get Info of package::

    yum info package

Install package::

    yum install package

To skip yes of installing::

    yum install -y package

List installed package::

    yum list installed package

Remove software::

    yum remove package

-> While uninstalling a package, the need dependencies get left behind and will NOT automatically be uninstalled. Because i could be that another package needs this dependency too.

To get sure, that depndencies are removed that only the package needs::

    yum autoremove package

To see if package is installed::

    which package

or

    yum list package

Repositories
============

To see which repositories are linked to the system::

    yum repolist

On RedHat-based systems repository information is saved in directory::

    etc/yum.repos.d

While listing with ls you can see that every repository has extension .repo.

Update Yum
===============

Clear cache of yum::

    yum clean all

Then updating yum::

    yum update


======================
RPM - Command
======================

Was the original command to install software on RedHat-based-Linux.
Where yum will check wich dependency is needed for the package, rpm does not. 
If dependencies are need, you have to locate those files, download and install them first. These came known as the "Dependecy Hell".

Rpm is still used for installing packages.

Install packages with::

    rpm -i package-2.13.e17.x86_64.rpm

-> Will install without any information prompted on the screen. To change that we can use 'v' (verbose) and 'h' for showing a progress bar.

So the command looks now like this::

    rpm -ivh package-2.13.e17.x86_64.rpm

Verify with 'which'-command

    which package

The query command of RPM
========================

To get the full package name, version and architecture::

    rpm -q package

To get full info add 'i' (for Info) to -q:

    rpm -qi package

-> Kind of the same output of yum info

To see which files are install use 'l'::

    rpm -ql package

To see documentation use 'd' (Documentation)::

    rpm -qd package

See wich dependencies are required ('R') for that package::

    rpm -qR package

Update package with 'U' ('Update')::

    rpm -Uvh package

Delete with 'e' ('Erase'):

Before deleting:
Yum is good for preventing us to destroy our system. With rpm a little more is required.

So we can --test with rpm for deleting the package, to make sure everything will work fine::

    rpm --test -e package

When no warnings appear -> Ready to delete::

    rpm -e package
    
    
======================
APT - Command
======================

Mainly, same as YUM-Command. One difference is that apt hast a file where all online locations are listed. Yum uses multiple .repo -Files.

at /etc/apt/source.list You can find this list

Update apt::

    apt update

Before, there should be some tests done:

To search for application::

    apt-cache search command

to install::

    apt install package

Verify and check with wich-command::

    which package

Remove package with::

    apt remove package

To uninstall any configuration files that probaply get left behind from the package with --purge.

    apt remove --purge package


To clean system up use "autoremove"::

    apt autoremove

To upgrade apt::

    apt upgrade

Full Upgrade any application::

    apt full-upgrade

======================
DPKG - Command
======================

In the past it was the main package command.
All Files are with .deb extensions.

To check if an application is already installed::

    dpkg --get-selection

-> Shows all Packages in the system

to get more information about the package (-I)::

    dpkg-deb -I package

Get info about package-name, version, architecture etc.

Install with -i option::

    dpkg -i package

-> If Error: Dependency problem::

    apt update
    apt -f upgrade

Kind of cheet. Chance that needed dependencies are installed from the cache.

To remove -r::

    dpkg -r package

To purge all configuration files that comes with the package -P::

    dpkg -P package
