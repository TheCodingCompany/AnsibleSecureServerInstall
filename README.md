Ansible Playbook

CentOS strong secure nGinx server setup with optional PHP-FPM and SSL preconfigured as well as PHPMyAdmin

Are you in need server support, managed server or security consultancy? 

https://www.thecodingcompany.se

#Ansible playbook roles

MariaDB
Webserver (phpMyAdmin optional)
Firewall
Common
OS Hardening

#Usage

1) change the values of SSL certificate in config.yml
2) choose if you want php and/or ssl
3) comment out roles you don't need
4) set the hostname in config.yml
5) add the IP of your machine(s) in hosts (under [server])
6) make sure the public key of the ansible server is in authorized keys on all machines added to hosts

use:  ansible-playbook -i hosts config.yml


#Create selfsigned certificate for phpMyAdmin
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/nginx-selfsigned.key -out /etc/nginx/ssl/nginx-selfsigned.crt
