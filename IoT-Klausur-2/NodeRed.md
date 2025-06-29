# NodeRed Installation & Set-Up

## Installing NodeRed

```
apt install npm
apt install nodejs
sudo npm install -g --unsafe-perm node-red
```

## Checking if the Service is UP and running

```
lsof -i -P
systemctl status node-red
```

## Enabling Auto-Start on NodeRed Service

```
npm install -g pm2
which node-red > determins the location of the Node-Red installation
pm2 start </path/to/node/red/> -- -v
```

```
pm2 save pm2 startup / pm2 startup systemd (> Heavily depends on the available Linux distro)
```

## Rebooting VM and double checking NodeRed Auto-Start

```
reboot now
lsof -i -P
systemctl status node-red
```
