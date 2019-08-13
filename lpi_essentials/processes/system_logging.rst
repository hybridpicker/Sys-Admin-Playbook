==============
System Logging
==============

Log Files are important for Sys-Admins.

Most are in /var/log::

    sudo cd /var/log
    
    boot.log.........contains messages when system boots
    
    messages.........Kind of daily newspaper for sysAdmins -> What is going on on System. When Troubleshooting -> the messages-log is always a good starting point.

    secure...........Defense report. Anytime user elevates privileges or logges in. -> secure-log

Kernel Ring Buffer
==================

The kernel ring buffer is a data structure that records messages related to the operation of the kernel. A ring buffer is a special kind of buffer that is always a constant size, removing the oldest messages when new messages come in. ::

    dmesg | less

Great place to start when troubles with hardware.
