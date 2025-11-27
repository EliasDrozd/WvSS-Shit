# VM Installation

## Basics

```
apt update

apt-get install apache2

apt-get install tor
```
## Configure your network


## Deleting default index.html

```
cd /var/www
ls -a
rm -r html

touch index.html
```

## Tor Configuration

```
nano /etc/tor/torrc

Hidden Services remove comment

nano /var/lib/tor/hidden_service/hostname
```

## Install Onion Router locally

paste the code from the hostname into it 
