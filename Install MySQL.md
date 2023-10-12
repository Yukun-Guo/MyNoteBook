# Install MySQL

## Install MySQL on Ubuntu

```bash
sudo apt update
sudo apt install mysql-server
sudo systemctl start mysql.service # start MySQL
```

## Configure MySQL

```bash
sudo mysql
```

Then run the following ALTER USER command to change the root user’s authentication method to one that uses a `password`(change to your own password).

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

Then exit MySQL:

```sql
exit
```

You can log into the MySQL shell with the following command:

```bash
mysql -u root -p
```

### Run the security script

```bash
sudo mysql_secure_installation
```

## Creating a Dedicated MySQL User and Granting Privileges

login to MySQL:

```bash
sudo mysql -u root -p
```

Once you have access to the MySQL prompt, you can create a new user with a CREATE USER statement. These follow this general syntax:

```sql
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```

After creating your new user, you can grant them the appropriate privileges. The general syntax for granting user privileges is as follows:

```sql
GRANT CREATE, ALTER, DROP, INSERT, UPDATE, INDEX, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'gyq'@'localhost' WITH GRANT OPTION;
```

Following this, it’s good practice to run the FLUSH PRIVILEGES command. This will free up any memory that the server cached as a result of the preceding CREATE USER and GRANT statements:

```sql
FLUSH PRIVILEGES;
```

## Reference

[How To Install MySQL on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04)