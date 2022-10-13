# webserver-php-script-install

#sudo apt update

#sudo apt install vim unzip curl wget -y

#sudo apt install apache2 -y

# upload your phpwebsite or php script to /var/www/yourwebsite-name

#sudo chown -R www-data:www-data /var/www/yourwebsite-name

# Create your virtual web server

#nano /etc/apache2/sites-available/yourwebsite-name.conf

# add this #

<VirtualHost *:80>
    ServerName your-domain.com    
    DocumentRoot /var/www/yourwebsite-name/public
 
    <Directory /var/www/yourwebsite-name/public>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>
    
</VirtualHost>

# add this #

#sudo a2enmod rewrite


