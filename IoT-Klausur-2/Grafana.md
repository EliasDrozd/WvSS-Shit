# Grafana Installation & Configuration

## Installing Grafana

```
sudo apt-get install -y apt-transport-https software-properties-common wget

sudo mkdir -p /etc/apt/keyrings/ wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null

echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

```
apt-get install grafana
```

## Reloading the Daemon

```
systemctl daemon-reload systemctl start grafana-server
```

## Checking if the Grafana Server is UP and running

```
systemctl status grafana-server

lsof -i -P / systemctl status grafana / grafana-server
```

## Enabling Auto-Start

```
systemctl enable grafana-server.service
```
