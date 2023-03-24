## Wordpress Info

Instead of installing wordpress using the `apt` command we will install manually 
because using `apt` for Wordpress is slightly more confusing.

Before installing software manually, check systems requirements for install and
ensure you are running the correct versions. PHP and MySQL require specififc
versions for Wordpress to install and run properly.
```
php --version
mysql --version
```

Install any extra modules needed. PHP needs the following installed to
operate WordPress at full functionality. After installing, restart apache2 and mysql.
```
sudo apt install php-curl php-xml php-imagick php-mbstring php-zip php-intl
sudo systemctl restart apache2
sudo systemctl restart mysql
```  
Next is to download and extract file.
Make sure you are in the correct directory `/var/www/html`

Use `sudo` to download the Wordpress program `wget` and then extract it.
```
sudo wget https://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
```

* Now you need to create a database and user for wordpress as the root
Linux user and the MySQL root user.
* Set up wp-config.php
* Change File ownership
 Follow steps here:
https://cseanburns.net/WWW/systems-librarianship/17-install-wordpress.html

* Run install Script
 - This part takes place in the browser not the command line. 
 - Make sure you have your correct IP address and navigate in the browser to 
following address using your IP in place of the text "youripaddresshere".
```
http://youripaddresshere/wordpress/wp-admin/install.php

* To finish install create a new username and password, keeping them in a
secure location.
* In this instance, we have not set up email on our servers so the email
 will not work. Choose whatever email you like, your gamil perhaps.
* make sure if you get an error once you naivgate to WordPress to set-up that you 
have **http** in the URL not **https** since we are using **http** not 
the secure **https**.

