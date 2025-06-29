# Installing & Configuring InfluxDB

## Installing InfluxDB & Client

```
apt install influxdb influxdb-client
```

## Checking if the DB is UP and running

```
systemctl status influxdb
lsof -i -P / systemctl status influxdb
```

## Opening influxdb

```
influx
```

## Creating the Databases

```
create database messung
show databases
```

## Selecting the created Database

```
use messung
```
