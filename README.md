# Project status
![status: inactive](https://img.shields.io/badge/status-inactive-red.svg)

This project is no longer actively maintained, and remains here as an archive of this work.

Setup the PHP InstantBuy Quickstart sample on your Webserver (Apache assumed here)
------------------------------------------------

Prerequisites:
-------------
1. You have a merchant id and a seller secret hereby referred to as MERCHANT_ID, MERCHANT_SECRET  (also known as seller secret)
2. You have already registered a Client ID for installed applications (https://code.google.com/apis/console/) and have the Client Id handy. This will be referred to in this README as CLIENT_ID.
3. You have an Apache server running

Getting Started
----------------
Setup Apache ModRewrite
Have the following in the httpd.conf within the Directory or VirtualHost directive. 

Options -MultiViews
 <IfModule mod_rewrite.c>
 RewriteEngine On
 RewriteBase /
 RewriteCond %{REQUEST_FILENAME} !-f
 RewriteCond %{REQUEST_FILENAME} !-d
 RewriteRule . /index.php [L,NC,QSA]
 </IfModule>

Alternatively you can create a .htaccess file in the Webserver root (usualy /var/www in Linux) with the following content
 RewriteEngine On
 RewriteBase /
 RewriteCond %{REQUEST_FILENAME} !-f
 RewriteCond %{REQUEST_FILENAME} !-d
 RewriteRule . /index.php [L,NC,QSA]

This is required to route all requests to the index.php which acts as Request router for the sample application.
Restart Apache by your favorite mechanism (on Linux sudo apachectl restart)


Set up the Project
------------------
1. Change the config.php values, Here all the constants are self explanatory and described in the config.php as well.
2. In the file index.php, replace ENTER_CLIENTID_HERE with your Client ID.
3. Copy all the PHP files to your server root


