# LAMP install notes

### Linux, Apache, MySQL, PHP

#### Simple Steps for Apache2 install

1. Update system prior to installing new packages
	```
	sudo apt update
	sudo apt upgrade
	```
2. Confirm package to install and install using following command
	```
	sudo apt installl apache2
	```
3. Check it is working with `systemctl`
	```
	systemctl list-unit-files apache2.service
	```
*  no issues with this install refer to following webpage for in depth instruction

https://cseanburns.net/WWW/systems-librarianship/14-installing-the-apache-web-server.html
