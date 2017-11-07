# Bitnami Alfresco Community Stack Installation on Centos 7

Install CentOS 7 minimal
set hostname: ```etalfresco.local```

```sh
yum clean all ; yum -y update
yum -y install net-tools mc wget open-vm-tools
yum -y install epel-release
yum -y install htop
```
Install pre-required packages:
```sh
yum -y install fontconfig libSM libICE libXrender libXext cups-libs libGLU perl-Data-Dumper
```
Open ports on firewall
```sh
firewall-cmd --add-port 80/tcp --permanent
firewall-cmd --add-port 8080/tcp --permanent
firewall-cmd --add-port 8443/tcp --permanent
firewall-cmd --add-port 7070/tcp --permanent
systemctl restart firewalld
```
Download Bitnami Alfresco Community Stack installer
```sh
mkdir alfresco
cd alfresco/
wget https://bitnami.com/redirect/to/162237/bitnami-alfresco-201707-1-linux-x64-installer.run
```
Install Bitnami Alfresco Community Stack:
```sh
chmod +x bitnami-alfresco-201707-1-linux-x64-installer.run
./bitnami-alfresco-201707-1-linux-x64-installer.run
 LibreOffice [Y/n] :Y
 Google Docs Integration [Y/n] :Y
 Solr4 [Y/n] :Y
 Is the selection above correct? [Y/n]: Y
 
 Login [user]:
 Password :
 Please confirm your password :
 Do you want to configure mail support? [y/N]: Y
     Default email provider:
     [1] GMail
     [2] Custom
 Please choose an option [1] : 1
 GMail address []: emir.enetel@gmail.com
 GMail password :
 Re-enter :
 
 Do you want to continue? [Y/n]:
 
 Select a folder [/opt/alfresco-201707-1]:
```
