# Configuracion de la BBDD para k3s

Solo es necesario una base de dato y un usuario que pueda escribir en ella. Así que se instala MariaDB y listo.

## Instalar MariaDB

```bash
sudo apt update
sudo apt install mariadb-server
sudo mysql_secure_installation
```

## Fix login to Mysql

Some systems like Ubuntu, mysql is using by default the UNIX auth_socket plugin.

Basically means that: db_users using it, will be "auth" by the system user credentias. You can see if your root user is set up like this by doing the following:

$ sudo mysql -u root # I had to use "sudo" since is new installation

mysql> USE mysql;
mysql> SELECT User, Host, plugin FROM mysql.user;

+------------------+-----------------------+
| User             | plugin                |
+------------------+-----------------------+
| root             | auth_socket           |
| mysql.sys        | mysql_native_password |
| debian-sys-maint | mysql_native_password |
+------------------+-----------------------+
As you can see in the query, the root user is using the auth_socket plugin

There are 2 ways to solve this:

You can set the root user to use the mysql_native_password plugin
You can create a new db_user with you system_user (recommended)
Option 1:

$ sudo mysql -u root # I had to use "sudo" since is new installation

mysql> USE mysql;
mysql> UPDATE user SET plugin='mysql_native_password' WHERE User='root';
mysql> FLUSH PRIVILEGES;
mysql> exit;

$ sudo service mysql restart

## Allow connections from any host

```mysql
[mysqld]
bind-address = 0.0.0.0 #Change from localhost to '0.0.0.0' (all zeros)
#skip-networking   #Comment out this line if it exits
#enable-named-pipe #Comment out this line if it exists
```

```bash
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;

CREATE USER 'username'@'%' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' WITH GRANT OPTION;

FLUSH PRIVILEGES;
```
