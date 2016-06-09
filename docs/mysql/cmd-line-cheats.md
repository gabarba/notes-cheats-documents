#MySQL Command Line Cheats/Notes

##Backup and Restore 

**Backup MySQL Database**
```Bash
mysqldump -u {USER_NAME} -p{PASSWORD} {DB_NAME} > {BACKUP_FILENAME}.sql
```

**Backup MySQL Database GZIP**
```Bash
mysqldump -u {USER_NAME} -p{PASSWORD} {DB_NAME} | gzip -9 > {BACKUP_FILENAME}.sql.gz
```

**Restoring MySQL Database**
```Bash
msyql -u {USER_NAME} -p{PASSWORD} {DB_NAME} < {BACKUP_FILENAME}.sql
```

**Restoring MySQL Database from GZIP**
```Bash
gunzip < {BACKUP_FILENAME}.sql.gz | msyql -u {USER_NAME} -p{PASSWORD} {DB_NAME}
```

##Users and Permissions

**Create MySQL User**
```MySQL
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```

**Grant Permissions (On Databases and Tables)**
```MySQL
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

**Grant Permissions (On Specific Database)**
```MySQL
GRANT ALL PRIVILEGES ON `{DB_NAME}` . * TO 'newuser'@'localhost';
```

**Show List of Users and Hosts**
```MySQL
select user,host from mysql.user;
```

**Show Users Permissions**
```MySQL
show grants for '{USER_NAME}'@'{HOST}';
```



###Additional References

* [MySQL Backup and Restore - Webcheatsheet.com](http://webcheatsheet.com/sql/mysql_backup_restore.php)
* [Compressing Mysqldump Output](http://www.ducea.com/2006/10/28/compressing-mysqldump-output/)
* [How to Create New MySQL User and Grant Permission](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql)
* [How to View Users and Permissions MySQL](http://xmodulo.com/how-to-view-list-of-mysql-users-and-their-privileges.html)