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
PGID=$(id -g $USER)
PUID=$UID
TZ="Europe/London"
SHARE="movies;/media/movies;yes;no;yes;all"
SHARE2="tv;/media/tv;yes;no;yes;all"
EXPORTS_FILE=/home/$USER/home-server/exports.txt
NFS_EXPORT_1="/media/movies 192.168.0.0/255.255.255.0(rw,async,insecure,no_subtree_check,all_squash,anonuid=$UID,anongid=$(id -g $USER))"
NFS_EXPORT_2="/media/tv 192.168.0.0/255.255.255.0(rw,async,insecure,no_subtree_check,all_squash,anonuid=$UID,anongid=$(id -g $USER))"
EOT
```
