# Koha 
* Current VM can’t support the data requirements of the Koha install so we need a new VM.
* Koha needs port 8080 open to allow traffic for staff to have access to a staff interface. We add this to our VM after it is created. This is a “firewall rule”. 
https://cseanburns.net/WWW/systems-librarianship/20-install-koha.html

* Begin as usual with `sudo` to spade and upgrade VM. 
	- Remember: `Sudo` gives you access as the root user without being logged in as the root user.
* Reboot machine
```
sudo reboot now
```
* Must log in as the root user to add a Koha repository to our server 
```
sudo su
```
For instructions how to add the repository look here:
https://cseanburns.net/WWW/systems-librarianship/20-install-koha.html

### Next is to Install and configure Koha using the instructions here: https://cseanburns.net/WWW/systems-librarianship/20-install-koha.html


Remember your username and password.
### To add patrons 
* To add new patrons go to patron link
    * do quick add
* To change the look of the presented categories in any Koha admin section use the Click “More” > administration > global system preferences
    *  Choose the appropriate section to edit
### To add bibliographic data by importing, make sure to have Z39.50/SRU targets to pull from. These are other libraries that freely share their MARC data.
- More info here: https://koha-community.org/manual/16.11/html/ch02s06.html#suggestztarget
