# set up a MySQL server on your Raspberry Pi.

### 1. The first thing we need to do is open the MySQL command line tool by running the following command.
    
    We will be using this command line tool to create a user and database for MySQL.

    --> sudo mysql -u root -p

### 2. Once you have logged in to the tool, we can start by creating a database. 
    
    We will be creating this database called nextclouddb by running the following command.

	--> CREATE DATABASE nextclouddb;

### 3. Our next step is to create a user that we will be using to interact with our new database. We will be creating a user called nextclouduser by running the command below. Make sure that you replace [PASSWORD] with a secure password and make note of it for later.

	--> CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY '[PASSWORD]';

### 4. With our user created we need to now give it permissions to interact with our database.

    We can do that by running the following command.
	
	--> GRANT ALL PRIVILEGES ON nextclouddb.* TO 'nextclouduser'@'localhost';

### 5. Our final task is to flush the privilege table.

    To flush the privileges all we need to do is run the following command.	

	--> FLUSH PRIVILEGES;

