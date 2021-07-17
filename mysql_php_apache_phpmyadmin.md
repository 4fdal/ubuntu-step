Install MySQL Database Server
```
sudo apt update
sudo apt install mysql-server mysql-client

CREATE USER 'afdal'@'localhost' IDENTIFIED BY 'password';

//permission per database table
GRANT PRIVILEGE ON database.table TO 'username'@'host';

//permission all database and table
GRANT PRIVILEGE ON *.* TO 'username'@'host';

//permission spesific access all database and table 
DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'username'@'host' WITH GRANT OPTION;

```

Install Apache2 HTTP Server
```
sudo apt install apache2
sudo nano /etc/apache2/mods-enabled/dir.conf
```

```
<IfModule mod_dir.c>
	DirectoryIndex index.html index.php index.xhtml index.htm
</IfModule>
```

```
sudo systemctl restart apache2.service
```

Install PHP and Related Modules
```
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt-get install php php-cgi libapache2-mod-php php-common php-pear php-mbstring
sudo a2enconf php8.0-cgi
```

Install phpMyAdmin
```
sudo apt-get install phpmyadmin php-gettext
```

```
+------------------------+ Configuring phpmyadmin +-------------------------+
 | Please choose the web server that should be automatically configured to   |
 | run phpMyAdmin.                                                           |
 |                                                                           |
 | Web server to reconfigure automatically:                                  |
 |                                                                           |
 |    [*] apache2                                                            |
 |    [ ] lighttpd                                                           |
 |                                                                           |
 |                                                                           |
 |                                 <ok>                                      |
 |                                                                           |
 +---------------------------------------------------------------------------+
```

```
sudo ln -s /usr/share/phpmyadmin /var/www/
sudo nano /etc/apache2/apache2.conf
```

Then add the following line:
```
Include /etc/phpmyadmin/apache.conf 
```


Remove
```
sudo apt purge mysql-server mysql-client
or
sudo apt purge mysql-server* mysql-client*
or 
sudo apt remove mysql-server mysql-client

sudo apt purge php php
or
sudo apt purge php* php*
or 
sudo apt remove php php

sudo apt purge apache2 apache2
or
sudo apt purge apache2* apache2*
or 
sudo apt remove apache2 apache2
```

















