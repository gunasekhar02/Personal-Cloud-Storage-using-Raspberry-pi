## Getting Nextcloud on your the Raspberry Pi is quite simple, it mainly involves downloading the zip file from their website, extracting it and then making some .

### 1. To get started let’s first move to our html directory with the following change directory command.

	--> cd /var/www/

### 2. Now we can download the latest version of Nextcloud to our device.
	To do this we will use wget to download the latest release to the current folder.

	--> sudo wget https://download.nextcloud.com/server/releases/latest.tar.bz2

### 3. With Nextcloud now downloaded to our Raspberry Pi, let us extract the archive.
	To extract the archive using tar we need to use the command below.

	--> sudo tar -xvf latest.tar.bz2

### 4. We now need to create a data directory for Nextcloud to operate in, for the initial setup of Nextcloud we must make this folder in our html/nextcloud directory.
	Create the directory by using the mkdir command as shown below:

	--> sudo mkdir -p /var/www/nextcloud/data

### 5. Now let’s give the correct user and group control over the entire Nextcloud folder and everything inside it.
       by running the following chown command.

	--> sudo chown -R www-data:www-data /var/www/nextcloud/

### 6. Finally we need to give it the right permissions, again run the following chmod command.

	--> sudo chmod 750 /var/www/nextcloud/data
