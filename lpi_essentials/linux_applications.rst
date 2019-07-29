===================
Common Applications
===================

***************
Desktop Apps:
***************

Word-OpenSource:

Libre Office Writer

Excel-OpenSource:

Libre Office Calc

Libre Office can open .doc.ppt etc Files

For install Apps we can use the AppInstaller -> For instance the GNU Image Manipulate Software -> Application GIMP

***************************
Common Desktop Environments 
***************************

- GNOME (most default)
- KDE
- XFCE
- Enlightment
- LXDE

*********************
Server Apps:
*********************

What is a Server?

A Server is a powerful Computer that serves data from itself to the client system.

A WebServer sends webpages to a user's application -> Like Firefox web browser to a computer

How does this work?

On one side: 

- Linux Server

             -> IP-Adress: 10.10.0.10

             -> Has a webserver that listens on Port 443

On other side: 

- Linux Desktop

               -> IP Adress: 10.10.0.15

Visualize Help: Compare to telephonesystem::

     IP Adress.... like a telephone number

     Port ...... Like Phone extension


Desktop makes a network call to that server - asking for a webpage. The server listens on port 443 for any incoming request. Wenn server see's that the Desktop wants wth IP 10.10.0.15 made a request -> sends webpage down to Desktop. This data will be renderd in the Browser.

IMPORTANT!:

********************
Common Network Ports
********************

Port Number -------- Protocol -------- Server Application
     
--------22--------------- SSH --------------OpenSSH

--------23-------------TELNET --------------telnetd

--------25---------------SMTP------------Postfix, SendMail

--------53---------------DNS----------BIND, named, unbound

--------67---------------BOOT------------dnsmasq, dhcpd

-------80---------------HTTP--------------Apache, Nginx

-------443---------------HTTPS-----------Apache, Nginx

***********************************
Other Important Server Applications
***********************************

File Server
===========

NFS: 

NetworkFileServer for filesharing between a server and client-system -> common on many UNIX Systems

SAMBA/CIS:

Give the opportunity to serve up files to Windows Clients on the same Network

Database Servers
================

MySQL:

-> now owend by oracle. 

clone named MariaDB (-> not owend by Oracle)


PostgresSQL:

more advanced tha MySQL

CUPS
====

CommonUnixPrintingServer -> open source printed server, primarliy developed by Apple
Makes it possible to print -> Printer Client
