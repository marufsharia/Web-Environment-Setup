# Web-Environment-Setup 
Environment Configuration for web programming such as php (Laravel)  , nodejs 🍺️

### Install Apache2
We’re going to be installing Apache2 web server… to do that, run the following commands 

> `sudo apt update` <br>
`sudo apt update`
---------
After installing, the commads below can be used to stop, start and enable Apache2 service to always start up with the server boots.

> `sudo systemctl stop apache2.service`
`sudo systemctl start apache2.service`
`sudo systemctl enable apache2.service`
-------

### Install PHP 7.2 and Related Modules
Laravel is based on PHP.so we’ll need to install it. To install PHP and related modules run the following commands 

* For php 7.2
> `sudo apt install php7.2 libapache2-mod-php7.2 php7.2-mbstring php7.2-xmlrpc php7.2-soap php7.2-gd php7.2-xml php7.2-cli php7.2-zip` 

* For php 7.3
> `sudo apt install php7.3 libapache2-mod-php7.3 php7.3-mbstring php7.3-xmlrpc php7.3-soap php7.3-gd php7.3-xml php7.3-cli php7.3-zip`
------
* Optional
After install PHP, run the commands below to open PHP-FPM default file.
>	`sudo nano /etc/php/7.2/apache2/php.ini`

Then make the change the following lines below in the file and save.

> `memory_limit = 256M`

>`upload_max_filesize = 64M`

> `cgi.fix_pathinfo=0`
 
------

### Install MySQL

Execute the following command to install mysql.

> `sudo apt install mysql-server`
> `sudo apt install php7.2-mysql`


### Install phpmyadmin 

> `sudo apt install phpmyadmin`

* Uninstall/remove phpmyadmin

> `sudo apt remove --purge phpmyadmin`






###  Install Composer to Download Laravel

Run the commands below to install composer package and install.
you must have curl package installed for the commands to work.. if not, just run the following command  to install curl.

>   `sudo apt install curl` 

 After installed curl , run the following command to install composer.
 
> `curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer`

---
## Error Fixing 
* The mysqli extension is missing.

> `sudo apt-get install php7.2-mysql`


* Restart apache2 server 
> `sudo service apache2 restart`

---
### Uninstall/Remove Apache2 php mysql phpmyadmin

> `sudo apt remove apache2 apache2-bin apache2-data apache2-utils libapache2-mod-php libapache2-mod-php7.0 php7.0-mysql php7.0-opcache php7.0-readline  mysql-client-5.7 mysql-client-core-5.7 mysql-common mysql-server mysql-server-5.7 mysql-server-core-5.7 php-mysql php7.0-mysql php-common php-mysql php7.0-cli php7.0-common php7.0-json`

<br>

---
## Bounus 

* Give write permission of a directory 
> `sudo chown -R www-data:www-data /var/www/html/`
> `sudo chmod -R 755 /var/www/html/`

#### Installing phpmyadmin theme

 + Note your phpMyAdmin version. You can see this on the bottom right corner of the phpMyAdmin home page. In my case, the version is 4.6.6deb5.
 
 + Go to this link [https://www.phpmyadmin.net/themes/#pma_4_6](https://www.phpmyadmin.net/themes/#pma_4_6)  and download the desired theme listed under the version number of your installation. Say you have downloaded the **fallen-0.3.zip** file.
 
 + After successfully download completed, extract the zip file paste it in theme directory  **/usr/share/phpmyadmin/themes/**
 
 + All most done  just need to restart apache server by the following command 
 
 > `sudo service apache2 restart`
 
 **Yahoooo done...** 😎️😎️😎️ 
 just open phpmyadmin in your favrouite browser and go **Appearance settings** and choose your last installed theme. 

