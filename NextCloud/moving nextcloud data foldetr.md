### With Nextcloud now safely installed we can now tweak the setup to both be more secure and a bit more useable. One of the first things we should do is move the data directory so it does not sit in our web accessible directory.


--> #### This is also the same way you would move your Nextcloud data directory onto a larger external hard drive rather than putting increased load onto the Raspberry Pi’s SD Card.


### 1. To get started let’s make our new directory for where we will store our data files.

To make it easy we will make a new folder at /var/nextcloud and move our data folder into there.

Create the folder by running the following command:

	--> sudo mkdir -p /var/nextcloud

### 2. With our new folder we created we will now move our data directory into it, this is easy to do thanks to the mv command.

To begin the move type in the following command:

	--> sudo mv -v /var/www/nextcloud/data /var/nextcloud/data

### 3. Now with the files moved over we can now modify the datadirectory configuration to point to our new directory.

First, let’s change to the config directory for Nextcloud with the following command.

	--> cd /var/www/nextcloud/config

### 4. We can now copy the config file to make a backup of the file, we can do this with the following command:

	--> sudo cp -p config.php config.php.bk

### 5. Finally let’s open up the config.php file for editing using nano.

	--> sudo nano config.php

### 6. Within this file we need to change the following line:

	Find> 'datadirectory' => '/var/www/nextcloud/data' ,

      Replace with> 'datadirectory' => '/var/nextcloud/data',

### 7. Now we can save and quit out of the file by pressing CTRL + X then Y and then ENTER.

### 8. As one last precuation we should make sure that the www-data user still has ownerships over our new folder.

	--> sudo chown -R www-data:www-data /var/nextcloud/data


