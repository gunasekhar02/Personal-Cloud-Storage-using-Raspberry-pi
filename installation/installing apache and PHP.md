## To run Nextcloud on the Raspberry Pi we will first need to install and setup Apache and PHP.

### make sure we will make use of the latest available version of PHP 8.

### 1. To get started let’s first update our package repositories with the following command:

       --> sudo apt update
           sudo apt upgrade

### 2. With that done, let’s now install apache with the following command:

       --> sudo apt install apache2

### 4. With Apache2 now installed onto the Raspberry Pi, we just need to install PHP and several of its packages.

 To install PHP and the packages we need, run the following command.
	
	--> sudo apt install php8.1 php8.1-gd php8.1-sqlite3 php8.1-curl php8.1-zip php8.1-xml php8.1-mbstring php8.1-mysql php8.1-bz2 php8.1-intl php-smbclient php8.1-imap php8.1-gmp libapache2-mod-php8.1

### 5. With Apache and PHP now installed there is one final thing we need to do, and that is to restart Apache.

You can do this now making use of the following command:
	
	--> sudo service apache2 restart
