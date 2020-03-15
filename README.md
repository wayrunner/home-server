Damon Morgan Home Server
========================

Setup home server

Installation
------------

  bash <(curl -s https://raw.githubusercontent.com/damonmorgan/home-server/master/ubuntu)
  
Create empty `ssh` file in boot directory and add wifi information to `wpa_supplicant.conf`: 
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}
```

What is installed
-----------------

* docker and docker-compose
* nfs server
* samba server
* wireguard server
* sshd
* fstab


```
cat <<EOT >> .env
CONTAINERS_CONFIG_PATH=$(pwd)
TV_DESTINATION_PATH=/media/storage/entertainment/tv
MOVIE_DESTINATION_PATH=/media/storage/entertainment/movies
PROCESSING_PATH=$(pwd)
BACKUP_PATH=/media/storage
PGID=$(id -g $USER)
PUID=$UID
TZ="Europe/London"
EOT
```