# Web-Environment-Setup 
Environment Configuration for web programming such as php (Laravel)  , nodejs 🍺️

### Install Apache2
We’re going to be installing Apache2 web server… to do that, run the following commands 

> `sudo apt update`
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
###  Install Composer to Download Laravel

Run the commands below to install composer package and install.
you must have curl package installed for the commands to work.. if not, just run the following command  to install curl.

>   `sudo apt install curl` 

 After installed curl , run the following command to install composer.
 
> `curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer`