#!/bin/bash

# EXPORT LANGUAGES
source /etc/profile.d/lang.sh
export LANG='en_US.UTF-8'
export LC_ALL='en_US.UTF-8'

# INSTALL DEPENDENCIES
yum install -y zlib-devel epel-release python36 python36-devel mysql-devel httpd-devel
yum -y groupinstall development
yum update -y

# COPY VirtualHost CONF
cp /var/www/basic_app/basic_app.conf /etc/httpd/conf.d/basic_app.conf

# BUILD MOD_WSGI AND INSTALL
wget "https://github.com/GrahamDumpleton/mod_wsgi/archive/4.5.14.tar.gz"
tar -xzf '4.5.14.tar.gz'
cd ./mod_wsgi-4.5.14
./configure --with-python=/usr/bin/python3.6
make
make install
cd ..
rm -rf mod_wsgi-4.5.14
rm 4.5.14.tar.gz
