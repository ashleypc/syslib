# LAMP install notes

#### Linux, Apache, MySQL, PHP

## Simple steps for Apache2 install

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
**no issues with this install, refer to following webpage for further instruction:**

https://cseanburns.net/WWW/systems-librarianship/14-installing-the-apache-web-server.html

## Simple steps for installing and configuring PHP

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
	
**no issues with this install, refer to following webpage for further instruction:**

https://cseanburns.net/WWW/systems-librarianship/15-installing-configuring-php.html

## MySQL notes

1. Install MySQL
2. Log in under root account
	- be cautious as the root user!
	- remember `\q` to exit
3. Create a **regular user** so that we don't need to use **root user**
4. Create a practice database such as **opacdb**
	- this is where you set the **user** and their **permissions**
	- Exit out of the database as the **root MySQL user** and out of **root Linux user account**
	```
	\q
	root@hostname:~# exit
	```
#### How to log-in as regular user
1. Enter following command and input the password you created earlier for the user. Password will not show when you type or paste it in but it IS there!
	```
	mysql -u opacuser -p
	```
2. How to view and select databases:
	```
	show databases;
	use databasenamehere;
	```
#### Things to remember in MySQL
* When using MySQL end all commands with the semicolon `;`
* When entering database data, if mistakes are made on the command line but you have pressed enter, you cannot go back to that line above to edit. Press `\c` to cancel and restart that data.
* if you have already added it you can delete the record
* remember `\q` to quit the database

**no issues with MySQL install, refer to following webpage for further instruction:**

https://cseanburns.net/WWW/systems-librarianship/16-installing-configuring-mysql.html

