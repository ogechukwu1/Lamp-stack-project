# Lamp-stack-project

## Lamp stack

__Lamp stack__ is a bundle of 4 different software technologies that developers use to build websites and web applications.

__L__ stands for __linux__ (the operating system-ubuntu)

__A__ stands for __Apache__ (the web server-HTTP server)

__M__ stands for __mysql__ (the database server)

__P__ stands for __php__ (the programming language)


__let's get started with the installation__


_let's launch an instance on our AWS account, give it any name of your choice_


![](./images/2.png)

_choose ubuntu OS_

![](./images/3.png)

_create a keypair_

![](./images/4.png)

_create a security group, to allow HTTPS traffic and lauch instance_

![](./images/5.png)

_let's ssh into our ubuntu terminal_

`ssh -i Downloads/jenkinskey.pem ubuntu@54.219.139.207`

_downloads: is where your keypair is kept_

_jenkinskey.pem: is the name of your keypair_

_ubuntu: is the name of your server_

_54.219.139.207: is the ip address_

![](./images/6.png)

__let's install apache2__

_first we update ,so that all the latest applications can be installed smoothly._

`sudo apt update`

![](./images/7.png)

`sudo apt install apache2`

![](./images/8.png)

_you need to adjust your firewall settings to allow HTTP traffic. Ubuntu default firewall configuration tool is called (__uncomplicated firewall-ufw__)_

_to list and open all available firewall_

`sudo ufw app list`

![](./images/9.png)

_to allow traffic on port 80_

`sudo ufw allow in "Apache full"`

![](./images/10.png)

_to check if the service is running_

`sudo systemctl status apache2`

![](./images/13.png)

_to view the outcome of your work, you paste your ip address on your website_

![](./images/11.png)

_to check where your configuration site for your website are:_

`cd /etc/apache2/`

![](./images/14.png)

_then cd into the available sites_

`cd /sites-available/`

![](./images/15.png)

![](./images/16.png)

`vim 000-default.conf`

![](./images/17.png)









__MYSQL-SERVER__

_mysql is mostly used as database and to store data_

_lets install __mysql-server___

`sudo apt install mysql-server`

![](./images/21.png)

 _check the version_

 `mysql --version`

 ![](./images/23.png)

 _to check if the service is running_

 `sudo systemctl status mysql.service`

 ![](./images/24.png)

 _let's do some configurations_

 `sudo mysql_secure_installation`

 ![](./images/26.png)

`sudo mysql`

![](./images/22.png)

 _to set password as "Password1@" for root user_

 `ALTER USER 'root'@'localhost'  IDENTIFIED WITH mysql_native_password BY  'Password1@' `

 ![](./images/29.png)

 _then "exit"_

![](./images/30.png)

_log into mysql using the password_

`sudo mysql -p`

![](./images/31.png)

_then"exit"_






__INSTALLING PHP__

_let's install php_

`sudo apt install php libapache2 -mod-php php-mysql`

![](./images/32.png)

_after installing, you can check the version_

`php -v`

![](./images/33.png)

_in order to verify that PHP is running on the server, we create a file in web root directory located at `/var/www/html/`_

_Create a file in the web root directory:_

`sudo nano /var/www/html/info.php`

![](./images/36.png)

_inside the file, type the PHP code:_


`<?php`

`phpinfo ();`

`?>`

![](./images/35.png)


_Press `CTRL + X` to save and close the file. Press `y` and `ENTER` to confirm._

_then open your internet browser and type the ip address_

_copy the ip address_

![](./images/37.png)

`[server-ip-address]/info.php`

![](./images/38.png)

_Here is the detailed output of __LAMP STACK WEBSITE___

![](./images/39.png)







































































































