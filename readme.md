# docker containers for em-demo

## mosquitto

* build

```
cd mosquitto
sudo docker build -t demo-mosquitto .
```

* run

```
sudo docker run -p 1883:1883 -d demo-mosquitto
```

## influxdb

* build

```
cd influxdb
sudo docker build -t demo-influxdb .
```

* run

```
sudo docker run -p 8083:8083 -p 8086:8086 -d demo-influxdb
```

* after

accsess admin UI with port 8083, then create database likewise 'mydb'

## grafana

* build

```
cd grafana
sudo ./build.sh
```

* run

```
sudo docker run -p 3000:3000 -d grafana:latest
```

* after

accsess GUI console with port 3000, then edit graph setting


## ifogcloud

* pre build

edit ``server_conf.yaml`` and ``monitor_conf.yaml`` to match your setting.

* build

```
cd ifogcloud
sudo docker build -t demo-ifogcloud .
```

* run

```
sudo docker run -e NODE_ENV=production -p 3001:3000 -d demo-ifogcloud
```
