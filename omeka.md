# Omeka Install

1. Update system
```
sudo apt update
sudo apt upgrade
```

2. install `unzip` program
```
sudo apt install unzip
```
3. Install prerequisites: `imagemagick` untilities and `mod_rewrite` for Apache2 then restart Apache 2
https://cseanburns.net/WWW/systems-librarianship/18-install-omeka.html

4.  Download Omeka Classic and unzip file
```
/var/www/html
wget https://github.com/omeka/Omeka/releases/download/v3.1/omeka-3.1.zip
unzip omeka-3.1.zip
```
5. Optional: Rename omeka-3.1 to omeka using `sudo mv`
6. Create the database and user in MySql
	- login as root linux user then root mysql user
```
sudo su
mysql -u root
```

 * create new user
 * replace XXXXXXXX with strong password
 * create new database
 * grant priveleges for omeka
 * check the output by showing the databases
 * exit MySQL
	
```
create user ‘omeka’@‘localhost’ identified by 'XXXXXXXXX';
create database omeka;
grant all privileges on omeka.* to ‘omeka’@‘localhost’;
show databases;
\q
```
7. Set up log-in credetials in the db.ini file
	- remember you can use `ls` to view the files and directories. 
	- look for omeka and `cd` to omeka then use `ls` again to see the db.ini file
	- remember to use sudo nano to open file if you have exited out of the root user above. *!Highly recommend that you exit root user to avoid major mistakes!*
repalce all XXXXXXX values with the ones you created
```
cd /var/www/html
sudo nano db.ini 
```
8. Change file ownership
```
sudo chown -R www-data:www-data *
```
9. Restart MySql and Apache2
```
sudo systemctl restart apache2
sudo systemctl restart mysql
```
10. Complete setup in browser at your IP address `/omeka`
 * `/omeka/admin` to log in and edit items after instal and gonfiguration is completed
