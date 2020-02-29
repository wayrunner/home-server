Damon Morgan Home Server
========================

Setup home server

Installation
------------

  bash <(curl -s https://raw.githubusercontent.com/damonmorgan/home-server/master/ubuntu)

What is installed
-----------------

* docker and docker-compose
* nfs server
* samba server
* wireguard server
* sshd
* fstab

* Configure .env with your local parameters.
```
cat <<EOT >> .env
SHARE_DATA_PATH=/media
EOT
```
