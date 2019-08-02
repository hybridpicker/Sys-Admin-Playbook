*******
$PATH
*******

How Linux executes command from the bash-prompt:

-> First it needs to know where the command is. Like ::

    which ls

    alias ls='ls --color=auto'
    	/usr/bin/ls

-> Command is in the bin-directory. So if we type that /bin/ls it's the same like 'ls' ::

    /bin/ls
        backup	backup.tar  find  shopping.txt

    ls
        backup  backup.tar  find  shopping.txt
    
This is because of the environment-variables. We can checkout with 'env'-command::

    env

In the PATH-Environment-Variable list all directory that bash will look in if we type in a command::

    PATH=/home/centos/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/centos/.local/bin:/home/centos/bin

colon stands for seperation, so it can look into more that one directory for a command.

Another way to find that PATH is with command 'echo'. Echo prints out what follows to the screen ::

   echo $PATH
    /home/centos/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/centos/.local/bin:/home/centos/bin

Attention: Linux and Bash is always case sensitive! :: 

/home/user/hello.sh != /HOME/user/hello.sh
