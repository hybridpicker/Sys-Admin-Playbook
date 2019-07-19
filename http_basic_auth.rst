************************************
 Access Control with HTTP Basic Auth
************************************
Error Options in conf
======================

/etc/nginx/conf.d/default.conf::
    
   server {
    ...
    location = /admin.html {
        auth_basic "Login Required";
        auth_basic_user_file /etc/nginx/.httpasswd;
    }
    ...
    }

Create admin page::

    echo "<h1>Admin Page</h1>" > /usr/share/nginx/html/admin.html

Install httpd-Tools to generate Password for admin::

    yum install -y httpd-tools

Generate password for User::

    htpasswd -c /etc/nginx/.httpasswd admin

Curl to Admin-Page::

    curl localhost/admin.html

        <html>
        <head><title>401 Authorization Required</title></head>
        <body>
        <center><h1>401 Authorization Required</h1></center>
        <hr><center>nginx/1.16.0</center>
        </body>
        </html>
