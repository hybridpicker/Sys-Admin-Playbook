******************
Basic Centos Setup
******************
================================
For Python 3.7 - Django Projects
================================

Install Packages into CentOs::

    $ sudo su -
    $ yum update
    $ yum groupinstall -y "development tools"
    $ yum install -y \
      gcc \
      lsof \
      wget \
      vim-enhanced \
      words \
      which
    $ exit

Git-Setup::

    $ sudo yum install git
    $ git config --global user.name "My Name"
    $ git config --global user.email "mymail@foo.com"

Bash-Setup::

    $ curl https://raw.githubusercontent.com/linuxacademy/content-python3-sysadmin/master/helpers/bashrc -o ~/.bashrc


Vim Setup::

    $ curl https://raw.githubusercontent.com/linuxacademy/content-python3-sysadmin/master/helpers/vimrc -o ~/.vimrc


===============
Install Python
===============

Install Python 3.7::

    $ sudo su -
    [root] $ yum install -y \
      libffi-devel \
      zlib-devel \
      bzip2-devel \
      openssl-devel \
      ncurses-devel \
      sqlite-devel \
      readline-devel \
      tk-devel \
      gdbm-devel \
      db4-devel \
      libpcap-devel \
      xz-devel \
      expat-devel
    
    [root ] $ cd /usr/src
    [root ] $ wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz
    [root ] $ tar xf Python-3.7.4.tgz
    [root ] $ cd Python-3.7.4
    [root ] $ ./configure --enable-optimizations
    [root ] $ make altinstall
    [root ] $ exit

=======================================================
Install and Configure VirtualEnv and VirtualEnvWrapper
=======================================================

We will be installing both of these components using pip, the Python package manager. To get pip, we first need to enable the EPEL repository. We can do this easily by typing::

    sudo yum install epel-release

Once EPEL is enabled, we can install pip by typing::

    sudo yum install python-pip
    
Now that you have pip installed, we can install virtualenv and virtualenvwrapper globally by typing::

    sudo pip install virtualenv virtualenvwrapper
    
With these components installed, we can now configure our shell with the information it needs to work with the virtualenvwrapper script. Our virtual environments will all be placed within a directory in our home folder called Env for easy access. This is configured through an environmental variable called WORKON_HOME. We can add this to our shell initialization script and can source the virtual environment wrapper script.

To add the appropriate lines to your shell initialization script, you need to run the following commands::

    echo "export WORKON_HOME=~/Env" >> ~/.bashrc
    echo "source /usr/bin/virtualenvwrapper.sh" >> ~/.bashrc

Now, source your shell initialization script so that you can use this functionality in your current session:

    source ~/.bashrc

You should now have directory called Env in your home folder which will hold virtual environment information.


===============
Install Django
===============

Steps fo installing Django::

    sudo yum install epel-release
    sudo yum update -y && sudo reboot

    sudo yum install python-devel python-setuptools python34 python-pip
    yum -y install python-pip python-wheel
    
    django-admin.py startproject firstsite


================
Install Postgres
================

Sudo install::

    sudo yum install postgresql-server postgresql-contrib

Initialize Database::

    sudo postgresql-setup initdb
    sudo systemctl start postgresql
    sudo systemctl enable postgresql

Changing password for user postgres::

   sudo passwd postgres

Create another role using “postgres”:
Creating new role “dbrnd”. -p = set the password and -d = allow to create database::

    sudo -u postgres createuser root -d -P

Edit pg_hba.conf::

    # IPv4 local connections:
    host    all             all             127.0.0.1/32            md5
    # IPv6 local connections:
    host    all             all             ::1/128                 md5

Restart Postgres::

    sudo service postgresql restart


Udpate pip::

    pip install -U pip
    pip install -U virtualenv

==================
Create Virtualenv
==================

Create your first virtual environment with the name of your first site or project by typing::

    which python3 #Output: /usr/bin/python3
    mkvirtualenv --python=/usr/bin/python3 nameOfEnvironment

    pip install django


================
Setup Postgres
================

Install Pyscopg::

     pip install psycopg2-binary


*settings.py*::

    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'dbmame',
            'USER': 'user',
            'PASSWORD': 'swordfish',
            'HOST': 'localhost',
            'PORT': '5432',
        }
    }

    ...

    if os.path.isfile(os.path.join(BASE_DIR, 'local_settings.py')):
        from local_settings import *

========================================
Backing Out of the Virtual Environment
========================================

Since we are now done with the Django portion of the guide, we can deactivate our virtual environment::

    deactivate
    
If you need to work on either of your Django sites again, you should reactivate their respective environments. You can do that by using the workon command ::

    workon envName
