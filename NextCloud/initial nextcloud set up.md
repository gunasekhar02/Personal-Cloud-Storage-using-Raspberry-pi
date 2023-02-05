## 1. Now that we have finished with that we can now finally go to Nextcloud itself and begin its installation process.


To begin go to your Raspberry Pi’s IP address plus /nextcloud.

If you don’t know your Raspberry Pi’s IP address you can make use of the command hostname -I.

Remember to replace [IPADDRESS] with that of your Raspberry Pi’s.

	--> [IPADDRESS]/nextcloud

## 2. You will now be greeted with the following screen.

Here you will need to type in the Username and Password (1.) that you intend to use for your admin account.

If you plan on allowing your Nextcloud file service to be accessible from outside your network, make sure that you use a long and secure password.

Next, we need to specify the details for our database server. To get to these options you will need to click the “Storage & Datbase” option (2.).

Now you need to slect the type of database we want to use. As we are using an SQL server click the “MySQL/MariaDB” (3.) option.

Finally we need to enter the details for our database server. There are three bits of information that we will need to enter.

1. The username for the user that will interact with our database server. (A.) If you are using the same information we used, this setting should be set to nextclouduser.
2. The password that you set for the above user. (B.)
3. The final option you will need to set is the database name. (C.) If you have been following our guide this will be nextclouddb.
4. Once you are happy with this, press the “Finish Setup” button (4.), please note this can take some time to complete as it finalises your setup.

### 3. After this you should now be greeted with the following welcome screen, this just lays out the various programs you can use to connect with your Nextcloud installation.

    Just click the X button in the top right corner to continue.

### 4. Now you can finally see the interface of the Raspberry Pi Nextcloud, you should take some time to familiarize yourself with all the functionality of Nextcloud’s interface.