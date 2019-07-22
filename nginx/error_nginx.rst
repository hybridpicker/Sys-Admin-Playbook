***************
Error on Nginx
***************
Error Options in conf
======================

/etc/nginx/conf.d/default.conf::
    
    server {
        ...
        error_page 404 /404.html;
        error_page 500 502 503 504 /50x.html;
     }

Check if Error-Pages exist::

    ls /usr/share/nginx/html/
