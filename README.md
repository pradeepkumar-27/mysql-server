# MYSQL Server installation on RHEL8
To install MySQL Server on Red Hat Enterprise Linux 8 (RHEL 8), you can follow these steps:

Update the system packages:
```
sudo dnf update
```
Install the MySQL repository configuration package:
```
sudo dnf install https://dev.mysql.com/get/mysql80-community-release-el8-1.noarch.rpm
```
Install the MySQL Server package:
```
sudo dnf install mysql-server
```
Start the MySQL service:
```
sudo systemctl start mysqld
```
(Optional) Enable MySQL to start on system boot:
```
sudo systemctl enable mysqld
```
Retrieve the temporary root password created during installation:
```
sudo grep 'temporary password' /var/log/mysqld.log
```
Note down the generated temporary password as you'll need it to secure the MySQL installation.

Run the MySQL secure installation script:
```
sudo mysql_secure_installation
```
The script will guide you through the process of securing the MySQL installation, including setting a new root password, removing anonymous users, disallowing root login remotely, and removing the test database.

Access the MySQL server:
```
sudo mysql -u root -p
```
Enter the new root password that you set during the secure installation.

Congratulations! You have successfully installed and secured MySQL Server on Red Hat Enterprise Linux 8. You can now use the MySQL command-line client to interact with the database server.