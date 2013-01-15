cnxcc-web
=========

Web management interface for cnxcc module.

Updates
=========
- Still under development.

Installation
=========

0. Create a new user, "cnxcc" for example (this is not mandatory, but it is recommended).
<pre>
    # useradd cnxcc -m
    # su - cnxcc
</pre>

1. Go to your installation directory and clone the repository
<pre>
    $ git clone git://github.com/caruizdiaz/cnxcc-web.git
</pre>

2. Grant read/execute permissions over your directory
<pre>
    # chmod 755 /home/cnxcc/
</pre>

3. Create a virtual host configuration file for apache, pointing the document root to the public directory of your
recently cloned repository
<pre>
    # vim /etc/httpd/conf/cnxcc.conf
</pre>
<pre>
    <VirtualHost 1.2.3.4:80>
        DocumentRoot /home/cnxcc/cnxcc-web/public
        ErrorLog /var/log/httpd/cnxcc-error_log
        <Directory /home/cnxcc/cnxcc-web/public/>
            Options Indexes FollowSymLinks MultiViews
            DirectoryIndex index.php
            AllowOverride All
            Order allow,deny
            Allow from all
        </Directory>
    </VirtualHost>
</pre>

<pre>
# /etc/init.d/httpd restart
</pre>

4. Create the database
<pre>
    # mysql < /home/cnxcc/cnxcc-web/sql/cnxcc.sql
</pre>

5. Now the page should be accessible. Go to http://1.2.3.4 and try it

6. Configure the database synchronization following these instructions
<pre>
    https://github.com/caruizdiaz/cnxcc-db-sync/blob/master/README.md
</pre>

Screenshots
=========
![ScreenShot](http://caruizdiaz.com/wp-content/uploads/2013/01/cnxcc-1024x433.png)
![ScreenShot](http://caruizdiaz.com/wp-content/uploads/2013/01/cnxcc1-1024x506.png)
