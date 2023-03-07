* html code will refer to the php script which we create separately. Html provides the user interface.

* The php is needed to communicate and add the data from the html form into the database

### Always make page secure using authentication file.

1. cd to `/etc/apache2`
2. Set username as **libcat** and pick own password (choose own username was well make sure to set it in the code)
	```sudo htpasswd -c /etc/apache2/.htpasswd libcat```
3. Use apache2.conf file to tell Apache2 that we will use the htpasswd to control access by modifying the apache2.conf file. Further instruction here: https://cseanburns.net/WWW/systems-librarianship/16.8-basic-opac-admin.html
4. Check that the configuration file is okay
	```
	apachectl configtest
	```
5. Restart Apache2 if Syntax OK message appears, otherwise recheck previous steps for errors/typos.
	```
	sudo systemctl restart apache2
	systemctl status apache2
	```
