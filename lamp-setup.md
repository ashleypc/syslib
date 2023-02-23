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
* no issues with this install, refer to following webpage for further instruction:

https://cseanburns.net/WWW/systems-librarianship/15-installing-configuring-php.html
