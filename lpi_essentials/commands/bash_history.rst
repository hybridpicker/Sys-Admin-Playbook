************************************
Bash History and Command Completion
************************************

Command history is found in .bash_history -> hidden in the home directory. This file contains a log of commands entered at the Bash prompt

With the 'cat'-Command (stands for -> Getting file to the screen) we can print out .bash_history ::

    cat .bash_history

        ls
        cd djangoproj_nginx.conf
        vim djangoproj_nginx.conf
        systemctl restart nginx
        sudo su -
        ls
        cd proc/sys
        sudo su -
        cd
        cd ~l
        cd ~
        ls
        rm -rf mysote-sock
        ls
        rm -rf mysite-sock
        rm -rf mysite.sock
        ls
        logout

To manage how bash stores command history we can do that with the $HISTCONTROL - Value::

    echo $HISTCONTROL 
        ignoredups

'ignoredups' stands for -> hiding duplicate commands

'history' command prints the content of .bash_history and each command has a number ::

 history
    1  cd
    2  ls
    3  sudo su -
    4  logout
    5  sudo su -
    6  git config --global user.name "hybridpicker"
    7  sudo yum install git
    8  git config --global user.name "hybridpicker"

if there is a particular command we want to run again, we can do that with telling bash the number of this command - based on the history::

    !<number of command>

     !535
    ls -a
    .   archive        .bash_logout   .bashrc  .gitconfig  logs  publicdir  .python_history  .ssh  .viminfo
    ..  .bash_history  .bash_profile  .cache   lfcs        .pki  python     scripts          .vim  .vimrc

Tab Completion
==================

With pressing the 'TAB'-Key, Linux autocompletes the commands and directory. ::

    $ his -> $ history

Also works with directories ::

    cd ./pyth -> cd ./python/
