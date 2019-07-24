====================================
Troubleshoot and Install Bootloaders
====================================

get grub File::

    cat /boot/grub/grub.conf

- automatic generated

-> comes from updategrub

Menu entries for entries::

    cd /etc/grub.d
    ls -la


    -rwxr-xr-x.  1 root root  8702 Jan 30 13:58 00_header
    -rwxr-xr-x.  1 root root  1043 Jul  4  2018 00_tuned
    -rwxr-xr-x.  1 root root   232 Jan 30 13:58 01_users
    -rwxr-xr-x.  1 root root 10781 Jan 30 13:58 10_linux
    -rwxr-xr-x.  1 root root 10275 Jan 30 13:58 20_linux_xen
    -rwxr-xr-x.  1 root root  2559 Jan 30 13:58 20_ppc_terminfo
    -rwxr-xr-x.  1 root root 11169 Jan 30 13:58 30_os-prober
    -rwxr-xr-x.  1 root root   214 Jan 30 13:58 40_custom
    -rwxr-xr-x.  1 root root   216 Jan 30 13:58 41_custom

These are numberd because it is runned in thtat order.

To create new grub file always start with template in /etc/default/grub::

    less/etc/default/grub.

    GRUB_TIMEOUT=1
    GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
    GRUB_DEFAULT=saved
    GRUB_DISABLE_SUBMENU=true
    GRUB_TERMINAL="serial console"
    GRUB_SERIAL_COMMAND="serial --speed=115200"
    GRUB_CMDLINE_LINUX="console=tty0 crashkernel=auto console=ttyS0,115200"
    GRUB_DISABLE_RECOVERY="true"



Example File::

    sudo vim 15_hybridpicker_test

-> See in Git (also 15_windows)

Don't forget for giving the rights to execute::

    sudo chmod +x 15_hybridpicker_test

WIKI for Grub::
    
    https://www.supergrubdisk.org/
    https://wiki.ubuntuusers.de/GRUB_2/
