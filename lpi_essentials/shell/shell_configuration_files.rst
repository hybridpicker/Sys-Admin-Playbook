**************************
Shell Configuration Files
**************************

At first we need to discuss the difference between Log-in and not-log-in-Shell

Login Shell
===============

- Connected to a Linux System with SSH
- Even with a graphical desktop

During a login shell, these configuraiton script files are called in this order:

- etc/profile

(-> This file is setting up all default user environments and any scripts for user login)

The the order branches out, the first file that is found is used, all of the others are ignored even if they exist:

- ~/.bash_profile
- ~/.bash_login
- ~/.profile

Next, .bashrc is called, followed by /etc/bashrc

If .bash_logout exists everything when logging out will executed from this file.


Not Login Shell
================

- When using Terminal Application
- When a script is ran

When starting a non-login-shell it reads .bashrc File in the user home-directory
