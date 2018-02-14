# Ubuthu
Instalacion de Moodle 3.0

sudo apt-get install vim

sudo apt-get update

sudo apt-get install apache2 mysql-client mysql-server php7.0 libapache2-mod-php7.0

sudo apt-get install graphviz aspell ghostscript clamav php7.0-pspell php7.0-curl php7.0-gd php7.0-intl php7.0-mysql php7.0-xml php7.0-xmlrpc php7.0-ldap php7.0-zip php7.0-soap php7.0-mbstring

sudo service apache2 restart

sudo apt-get install git-core

cd /opt

sudo git clone git://git.moodle.org/moodle.git

cd moodle

sudo git branch -a

sudo git branch --track MOODLE_33_STABLE origin/MOODLE_33_STABLE

sudo git checkout MOODLE_33_STABLE

sudo cp -R /opt/moodle /var/www/html/

sudo mkdir /var/moodledata

sudo chown -R www-data /var/moodledata

sudo chmod -R 777 /var/moodledata

sudo chmod -R 0755 /var/www/html/moodle

sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf

default_storage_engine = innodb

innodb_file_per_table = 1

innodb_file_format = Barracuda

:w

:r

sudo service mysql restart

mysql -u root -p

CREATE DATABASE moodle DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;

create user 'moodledude'@'localhost' IDENTIFIED BY 'passwordformoodledude';

GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON moodle.* TO moodledude@localhost IDENTIFIED BY 'passwordformoodledude';

quit;

SELECT password('passwordformoodledude');

sudo chmod -R 777 /var/www/html/moodle

sudo chmod -R 0755 /var/www/html/moodle

sudo mkdir /var/quarantine

sudo chown -R www-data /var/quarantine

sudo vi /etc/php5/apache2/conf.d/05-opcache.ini

/etc/php/7.0/mods-available/opcache.ini

sudo service apache2 restart

cd /var/www/html/moodle/

sudo wget https://github.com/rlerdorf/opcache-status/blob/master/opcache.php

sudo vi /etc/apache2/sites-available/000-default.conf

:w :q

sudo service apache2 restart


----EJEMPLO 1-----

var


----EJEMPLO 2------

/var/www/html/moodle27/version.php:$release  = '2.7.14 (Build: 20160509)'

/var/www/html/moodle28/version.php:$release  = '2.8.12 (Build: 20160509)'

/var/www/html/moodle29/version.php:$release  = '2.9.6+ (Build: 20160520)'

/var/www/html/moodle30/version.php:$release  = '3.0.4+ (Build: 20160603)'

/var/www/html/moodle31/version.php:$release  = '3.1+ (Build: 20160603)'

git clone -b MOODLE_31_STABLE git://git.moodle.org/moodle.git moodle31

git clone git://git.moodle.org/moodle.git [nameofdir]

git branch --track MOODLE_2#_STABLE origin/MOODLE_2#_STABLE

git checkout MOODLE_2#_STABLE
