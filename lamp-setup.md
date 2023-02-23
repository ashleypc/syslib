# LAMP install notes

### Linux, Apache, MySQL, PHP

#### Simple steps for Apache2 install

1. Update system prior to installing new packages
	```
	sudo apt update
	sudo apt upgrade
	```
2. After confirming package to install using `apt search` install using following command
	```
	sudo apt installl apache2
	```
3. Check it is working with `systemctl`
	```
	systemctl list-unit-files apache2.service
	```
*  no issues with this install, refer to following webpage for further instruction:

https://cseanburns.net/WWW/systems-librarianship/14-installing-the-apache-web-server.html

#### Simple steps for installing and configuring PHP

1. Install PHP
	```
	sudo apt install php libapache2-mod-php
	```
2. Connect PHP and Apache2
	```
	sudo systemctl restart apache2
	```
3. Check status
	```
	systemctl status apache2
	```
4. Configure Apache2 for PHP *want file index.php first in line instead of the default index.html*
	```
	cd /etc/apache2/mods-enabled/
	sudo cp dir.conf dir.conf.bak
	sudo nano dir.conf
	```
	- Edit file line to look like this:
	```
	DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
	```
5. Check that it is working and get message **Syntax Ok**
	```
	apachectl configtest
	```
6. Restart Apache2 after changes are made
	```
	sudo systemctl reload apache2
	sudo systemctl restart apache2
	```
7. Create an index.php file
	
* no issues with this install, refer to following webpage for further instruction:

https://cseanburns.net/WWW/systems-librarianship/15-installing-configuring-php.html
