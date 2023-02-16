# Documentation of project-1 2023

## Lamp stack implementation

### Installing apache2 webserver

`sudo apt update`

![updating list of packages in package manager](./images/apache-sudo-apt-update.png)

`sudo apt install apache2`

![run apache2 package installation](./images/sudo-apt-install-apache-2.png)

`sudo systemctl status apache2`

![verifying apache2 is running](./images/sudo-systemctl-status-apache2.png)

`sudo apt upgrade`

![upgrading system](./images/sudo-apt-upgrade.png)

![upgrading system](./images/sudo-apt-upgrade-2.png)

open inbound port 80

![opening inbound port 80](./images/opening-inbound-port-80.png)

curl http://localhost:80

![curl command page 1](./images/curl-command-1.png)

![curl command page 2](./images/curl-command-2.png)

![curl command page 3](./images/curl-command-3.png)

![curl command page 4](./images/curl-command-4.png)

![curl command page 5](./images/curl-command-5.png)

![curl command page 6](./images/curl-command-6.png)

![curl command page 7](./images/curl-command-7.png)

[opening web browser with public ip](./images/public-ip-on-browser-apache2-default-page.png)

`curl -s http://169.254.169.254/latest/meta-data/public-ipv4`

![curl command -s](./images/curl-command-s.png)

Installing mysql-server

`sudo apt install mysql-server`

![installing mysql-server](./images/installing-mysql-server-image1.png)

![installing mysql-server](./images/installing-mysql-server-image2.png)

`sudo mysql`

[sudo mysql](./images/sudo-mysql.png)

`sudo mysql_secure_installation`

![mysql secure server installation](./images/sudo-mysql-secure-server-installation.png)

`sudo mysql -p`

![sudo mysql -p](./images/sudo-mysql--p.png)

Installing php

`sudo apt install php libapache2-mod-php php-mysql`

![installing php](./images/installing-php-1.png)

![installing php and dependencies](./images/installing-php-and-dependencies.png)

`php -v`

![confirming php version](./images/php--v.png)

Creating a virtual host for website using apache

`sudo mkdir /var/www/projectlamp`

`sudo chown -R $USER:$USER /var/www/projectlamp`

![creating and changing ownership of projectlamp directory](./images/creating-and-changing-ownwership-of-directory-projectlamp.png)

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

![projectlamp configuration file creation](./images/projectlamp-config-file.png)

`sudo ls /etc/apache2/sites-available`

![showing new file in sites available directory](./images/sites-available-directory.png)

`sudo a2ensite projectlamp`

![enabling virtual host](./images/enabling-virtual-host.png)

`sudo a2dissite 000-default`

![dissablin apache's default website](./images/dissabling-apaches-default-website.png)

`sudo apache2ctl config test`

![checking for syntax error in configuration](./images/checking-for-syntax-error-in-cofiguration.png)

`sudo systemctl reload apache 2`

![reloading apache 2](./images/reloading-apache2-for-changes-to-take-effect.png)

`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

![creating index.html file in projectlamp folder](./images/creating-index.html-file-in-projectlamp-folder.png)

[website url using IP](http://3.70.128.52:80)

[opening website using IP](./images/opening-website-using-IP.png)

`http://ec2-3-70-128-52.eu-central-1.compute.amazonaws.com`

![accessing website on browser with public DNS name](./images/accessing-website-with-public-DNS.png)

Enabling PHP on website

`sudo vim /etc/apache2/mods-enabled/dir.conf`

![changing order in which index.php file is listed](./images/changing-order-index.php.png)

![changing order in which index.php file is listed](./images/changing-order-index.php-2.png)

`sudo systemctl reload apache2`

`vim /var/www/projectlamp/index.php`

![Creating a new file named index.php inside your custom web root folder](./images/creating-new-index.php-file-inside-custom-web-root.png)

refresh page

![refreshed page](./images/refreshed-page.png)

`sudo rm /var/www/projectlamp/index.php`




























