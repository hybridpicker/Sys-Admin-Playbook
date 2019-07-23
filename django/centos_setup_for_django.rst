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

===============
Install Pip3
===============

Install python3-Tools and pip3::
    
    yum install python36
    yum install python36-devel
    yum install python36-setuptools
    easy_install-3.6 pip

==========================
Create Virtualenv Python 3
==========================

Create virtual env with python3::
    virtualenv -p python3 django3

===============
Install Django
===============

Steps fo installing Django::

    sudo yum install epel-release
    sudo yum update -y && sudo reboot

    sudo yum install python-devel python-setuptools python34 python-pip
    yum -y install python-pip python-wheel

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

Create virutalenv::

    python3.7 -mvenv env
    source env/bin/activate
    pip install --upgrade pip



Setup Postgres:

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

