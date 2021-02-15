
Change Root 

```
    ServerAdmin webmaster@localhost
    DocumentRoot /home/sysadmin/share
    <Directory />
        Options Indexes FollowSymLinks Includes ExecCGI
        AllowOverride All
        Require all granted
    </Directory>
```