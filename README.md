# odoo-9-installation-script

This script adds more but do not modify the version of Yenthe666. In facts, it combines the best of aschenkels-ictstudio & Yethe666 odoo 9 installation scripts. It uses Yenthe666 script as a templete and adds view commands from aschenkels-ictstudio script for postgres. 

The added commands do:
1. make UTF-8 the default language for postgres 
2. make postgres server listens to requests from any TCP/IP address.
3. restart postgres server to apply the modifications above




Below are the lines of code copied from aschenkels-ictstudio script. 
***********************************
sudo apt-get install -y locales
sudo export LANGUAGE=en_US.UTF-8
sudo export LANG=en_US.UTF-8
sudo export LC_ALL=en_US.UTF-8
sudo locale-gen en_US.UTF-8
sudo dpkg-reconfigure locales

echo -e "\n---- PostgreSQL $PG_VERSION Settings  ----"
sudo sed -i s/"#listen_addresses = 'localhost'"/"listen_addresses = '*'"/g /etc/postgresql/9.4/main/postgresql.conf

sudo service postgresql restart
***********************************
