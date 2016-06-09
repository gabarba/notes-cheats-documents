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

###Additional References
[MySQL Backup and Restore - Webcheatsheet.com][http://webcheatsheet.com/sql/mysql_backup_restore.php]
[Compressing Mysqldump Output](http://www.ducea.com/2006/10/28/compressing-mysqldump-output/)