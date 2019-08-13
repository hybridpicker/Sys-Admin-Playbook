****************************
Basic Network Configuration
****************************

IP (InternetProtocol) adress
=============================

Each computer on the network has an IP-Adress. 

Can be compared as a telephone number.

Subnet Mask (netmask) address
===============================

This address provides a more accurate description of the network the computer attached to.

A subnet mask is a number that defines a range of IP addresses available within a network. A single subnet mask limits the number of valid IPs for a specific network. Multiple subnet masks can organize a single network into smaller networks (called subnetworks or subnets). Systems within the same subnet can communicate directly with each other, while systems on different subnets must communicate through a router.

Gateway adress
===============

A gateway is a network node used in telecommunications that connects two networks with different transmission protocols together. Gateways serve as an entry and exit point for a network as all data must pass through or communicate with the gateway prior to being routed. In most IP-based networks, the only traffic that does not go through at least one gateway is traffic flowing among nodes on the same local area network (LAN) segment. The term default gateway or network gateway may also be used to describe the same concept.

DNS server adress
==================

Stands for Domain Name Services. 

More Network Settings
======================

================
Local IP adress
================

loopback::

    127.0.0.1

This adress is not accessible from other machines. It is mainly meant to be used on a per machine basis to test to see if the IP protocols are working on the system.

=====================
MAC (hardware) adress
=====================

Media Access control. A media access control address (MAC address) of a device is a unique identifier assigned to a network interface controller (NIC). For communications within a network segment, it is used as a network address for most IEEE 802 network technologies, including Ethernet, Wi-Fi, and Bluetooth.

Designed to uniquely identify each piece of hardware. 

=================
Routers
=================

Routers direct network traffic to their destinations. Collections of routing information are stored in 'routing tables'. To put it simply, a router connects devices within a network by forwarding data packets between them. This data can be sent between devices, or from devices to the internet. The router does this by assigning a local IP address to each of the devices on the network.
