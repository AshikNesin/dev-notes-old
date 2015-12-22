### To Install LAMP Stack
``` sudo apt-get install lamp-server^ ```

### To Install phpMyAdmin
``` sudo apt-get install phpmyadmin ```

-   You will need to configure your apache2.conf to make phpMyAdmin works.

    ``` nano /etc/apache2/apache2.conf ```

-   Then add the following line to the end of the file.

    ``` Include /etc/phpmyadmin/apache.conf ```
    
-   Then restart apache server.

    ``` sudo service apache2 restart ```

### Point domain name in Apache

``` sudo nano /etc/apache2/sites-available/000-default.conf ```

Refer https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts


sudo apt-get install unzip


### NodeJs

``` sudo apt-get install nodejs npm ```

to be on safer side 

``` ln -s /usr/bin/nodejs /usr/bin/node ```

### Enable mod_write in Apache



``` 
sudo a2enmod rewrite


sudo service apache2 restart


```

