### Now we should really work on setting up your Raspberry Pi Nextcloud server so that it runs through HTTPS and not plain HTTP.

### 1. Before we go modifying our Apache2 configuration we will first generate the self-signed certificate, luckily, we can do this all in one command thanks to OpenSSL.
Remember that a self-signed certificate will throw errors in your web browser and is not as secure as a properly signed certificate but it is better than nothing. It is also the only option if you’re not utilizing a domain name.

Before we generate the certificate, let’s first make a directory to store it.

	--> sudo mkdir -p /etc/apache2/ssl

### 2. Now let’s generate the certificate itself by running the following command in the terminal:

	--> sudo openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt

### you will See 

Country Name (2 letter code) [AU]:
State or Province Name (full name) [Some-State]:
Locality Name (eg, city) []:
Organization Name (eg, company) [Internet Widgits Pty Ltd]:
Organizational Unit Name (eg, section) []:
Common Name (e.g. server FQDN or YOUR name) []:
Email Address []:


### 3. Once you have filled out all that information we can then proceed on with setting up Apache2 to run SSL and to also utilize our newly generated certificate. This is a simple process but an important one.

First let’s enable the SSL module for Apache with the following command:

	--> sudo a2enmod ssl

### 4. Now we need to modify the default-ssl.conf file so it will utilize our new certificates and not the default ones that are generated by OpenSSL on installation.

To begin modifying this file run the following command:

	--> sudo nano /etc/apache2/sites-available/default-ssl.conf

### 5. Within this file we need to change the two lines below to point to our new certificates we generated into our /etc/apache2/ssl folder.

change 

find> 

SSLCertificateFile /etc/ssl/certs/ssl-cert-snakeoil.pem
SSLCertificateKeyFile /etc/ssl/private/ssl-cert-snakeoil.key

replace with>

SSLCertificateFile /etc/apache2/ssl/apache.crt
SSLCertificateKeyFile /etc/apache2/ssl/apache.key


### 6. Now we can save and quit out of the file by pressing CTRL + X then pressing Y and then Enter.

### 7. We can now enable the default-ssl configuration and restart Apache to load in our new configuration. We can do this with the following two commands.

	--> sudo a2ensite default-ssl.conf
	    sudo service apache2 restart

### 8. You can test to make sure this is working by going to your Raspberry Pi’s IP address with https:// in front of it.

GoTo>
	https://192.168.1.105/nextcloud