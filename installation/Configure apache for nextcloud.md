## Since we installed Nextcloud into the default Apache2 directory /var/www/, we will need to change some settings in Apache2 to allow the .htaccess file to override settings.


### To handle this just for the Nextcloud directory we will be creating a new configuration file for Apache.


### 1. To get started let’s create a file which will store our configuration changes for Nextcloud:

	--> sudo nano /etc/apache2/sites-available/nextcloud.conf

### 2. Now before you proceed any further you will need to decide whether you want Nextcloud to run under the “/nextcloud” directory or on its own domain or subdomain.

	I decided to run on my raspberry pi ip address.

	--> Alias /nextcloud "/var/www/nextcloud/"

	<Directory /var/www/nextcloud/>
 	  Require all granted
        AllowOverride All
        Options FollowSymLinks MultiViews

       <IfModule mod_dav.c>
        Dav off
       </IfModule>

       </Directory>

### 3.These lines basically tell Apache2 how to handle itself within the /var/www/nextcloud/ folder.

### 4. Now we can save and quit out of the file by pressing CTRL + X then pressing Y and then ENTER.

### With the file created we now need to tell Apache to make use of it.

    We can do this by utilizing the a2ensite command followed by nextcloud.conf.

	--> sudo a2ensite nextcloud.conf

### 6. Now we need to restart Apache2 to force it to read in the updated configuration file. 
	We can do that easily with the following command:

	--> sudo systemctl reload apache2