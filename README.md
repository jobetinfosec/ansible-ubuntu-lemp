# LEMP setup on Ubuntu 20.04 server


## Description

LEMP (Nginx, MariaDB and PHP 7.4) setup on Ubuntu 20.04 server.


## Tasks

* System update
* Install Nginx
* Removes default virtual host
* Creates new virtual host
* Creates web root directory for virtual host
* Uploads index.nginx-debian.html file
* Upload info.php file (delete it after test)
* Install PHP-FPM
* Configure php.ini
* Install MariaDB
* Sets MariaDB root password
* Removes all anonymous user accounts
* Removes the MariaDB test database


## Tested on

Ubuntu 20.04


## Requisites

a) Cloud Platform account<br />
b) A VPS server with Ubuntu 20.04 already installed<br />
c) An SSH key pair, with the public key already installed in the remote server<br />



## Instructions

a) On your laptop create a working directory


b) In your working directory open a console window


c) Clone github repository

```
git clone https://github.com/jobetinfosec/ansible-ubuntu-lemp.git
```


d) Switch to ansible-ubuntu-lemp role directory

```
cd ansible-ubuntu-lemp
```


e) Open the hosts file

```
nano hosts
```

f) Replace <TEMPORARY_ITEMS> with your own data:

`<SERVER_IP>`		replace <SERVER_IP> with the actual IP address of your remote server<br />
`<SUDO_USER_NAME>`	replace it with sudo user's name<br />
`<SUDO_USER_PASSWORD>`	replace it with sudo user's password<br />

then save and close the file


g) Open the defaults main.yml file

```
nano roles/lemp/defaults/main.yml
```

h) Replace <TEMPORARY_ITEMS> with your own data:

`<MYSQL_ROOT_PASSWORD>`	replace <MYSQL_ROOT_PASSWORD> with MariaDB root user's password<br />
`<DOMAIN_NAME>`		replace it with your domain name<br />
`<TIMEZONE>`		replace it with your timezone

then save and close the file


i) Check if you are able to ping remote server

```
ansible -m ping all
```

You should receive a SUCCESS message


j) Check if any error shows up

```
ansible-playbook lemp.yml --check
```


k) Launch installation

```
ansible-playbook lemp.yml
```

## Licence

MIT licence


## Author Information

Created by Roberto Jobet (sysadmin@wpsecurity.press).

Don't hesitate to open an Issue if you find any bug or have suggestions.
