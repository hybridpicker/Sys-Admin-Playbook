***************
Nginx on Centos
***************
Install Nginx
===============


Ressource::
    https://nginx.org/en/linux_packages.html

Create vim /etc/yum.repos.d/nginx.repo - File:

    vim /etc/yum.repos.d/nginx.repo

Paste from nginx.org::

    [nginx]
    name=nginx repo
    baseurl=http://nginx.org/packages/centos/7/$basearch/
    gpgcheck=0
    enabled=1

Install Ngnix::

    sudo yum install -y nginx

Start Ngnix::

    systemctl start nginx
    systemctl enable nginx

********************
Default Congif Nginx
********************
Remove Default Config
======================

Remove file and check if really removed::

    [root] $ systemctl reload nginx
    [root] $ curl localhost
    curl: (7) Failed connect to localhost:80; Connection refused

Server
======

to /etc/nginx/conf.d/default.conf::

    server {
        listen 80;
        root /usr/share/nginx/html;
    }

Testing if config worked::

     nginx -t

Reload::

    [root] $ systemctl reload nginx
    [root] $ curl localhost

Check if Error disapears::

    less var/log/nginx/error.log

    semanage fcontext -l | grep usr/share/nginx/html
    semanage fcontext -a -t httpd_sys_content_t '/var/www(/.*)?'
    restorecon -R -v /var/www

Check if template works::

    curl --header "Host: example.com" localhost
    curl --header "Host: www.example.com" localhost
