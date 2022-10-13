#sudo apt update

#sudo apt install vim unzip curl wget -y

#sudo apt install apache2 -y
#sudo service apache2 start
#sudo systemctl enable apache2

****** Install php ******
#sudo apt install libapache2-mod-php php-common php-bcmath php-mbstring php-mysql php-tokenizer php-zip php-curl php-xml openssl -y

**** upload your phpwebsite or php script to /var/www/yourwebsite-name  ****

#sudo chown -R www-data:www-data /var/www/yourwebsite-name

***** Create your virtual web server  ****

#nano /etc/apache2/sites-available/yourwebsite-name.conf

******* add this *******

<VirtualHost *:80>
    ServerName your-domain.com    
    DocumentRoot /var/www/yourwebsite-name/public
 
    <Directory /var/www/yourwebsite-name/public>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>
    
</VirtualHost>

******* add this *******

#sudo a2enmod rewrite

#sudo a2ensite yourwebsite-name	
#sudo systemctl restart apache2
#sudo a2dissite 000-default.conf
#sudo rm /var/www/html/index.html
#sudo systemctl restart apache2	


**** Installing and securing MariaDB *****

#sudo apt install mariadb-server mariadb-client
#sudo systemctl start mariadb
#sudo systemctl enable mariadb
#sudo mysql_secure_installation




*** Create databases for website ****

#sudo mysql -u root -p


create database webapps;
create user 'webapps'@'localhost' identified by 'Passw0rd';
grant all privileges on webapps.* to 'webapps'@'localhost';
flush privileges;
exit



