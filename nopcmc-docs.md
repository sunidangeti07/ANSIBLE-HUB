install Nopcommerce on ubuntu
------------------------------
* [refer here](https://docs.nopcommerce.com/en/installation-and-upgrading/installing-nop
commerce/installing-on-linux.html)
```
* nopCommerce is an open source eCommerce software that contains both a catalog 
  frontend and an administration tool backend.
* NopCommerce is an open-source e-commerce platform written in ASP.NET Core. It provides
 a comprehensive set of features for building and managing an online store, including
 product management, customer management, order management, payment and shipping options,
 and more.
* Before installing .NET Core, we'll need to register the Microsoft key and install the
 required dependencies. This needs to be done once per machine.
 ```
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb 
-O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```
Install the .NET Core Runtime
------------------------------
```
sudo apt-get update
sudo apt-get install -y apt-transport-https aspnetcore-runtime-7.0
```
* You can see all installed .Net Core runtimes by the following command:
```
dotnet --list-runtimes
```
Install nginx
--------------
```
sudo apt-get install nginx
sudo systemctl start nginx
sudo systemctl status nginx
sudo vi /etc/nginx/sites-available/default
```
* To configure nginx as a reverse proxy to forward requests to your ASP.NET Core app, 
modify /etc/nginx/sites-available/default. 

get Nopcommerce
----------------
```
mkdir /var/www/nopCommerce
cd /var/www/nopCommerce
sudo wget https://github.com/nopSolutions/nopCommerce/releases/download/release-4.60.1/no
pCommerce_4.60.1_NoSource_linux_x64.zip
sudo apt-get install unzip
sudo unzip nopCommerce_4.60.1_NoSource_linux_x64.zip
sudo mkdir bin
sudo mkdir logs
cd ..
sudo chgrp -R www-data nopCommerce/
sudo chown -R www-data nopCommerce/
sudo vi  /etc/systemd/system/nopCommerce.service
sudo systemctl start nopCommerce.service
sudo systemctl status nopCommerce.service
sudo systemctl restart nginx
```