# configuration manual

## mosquitto

no change is needed

## influxdb

After docker run, access admin console http://<YOUR_IP_ADDRESS>:8083/ . Then create **mydb** databbase.

```
CREATE DATABASE "mydb";
```

## ifogcloud

change config files below

* server_conf.yaml

change ``mqtt-handler->url`` IP address with your env.

change ``local-db->entrypoint`` IP address with your env.

* monitor_conf.yaml

get api-key from https://skyway.io (don't forget to set your IP address for API-KEY setting)
then apply it to ``modules->skyway->key``

change **history chart's entrypoint** url of ``components``


## raspberry pi

ssh raspberry PI, then change

* signalinggateway/conf/skyway.json

  - apikey : your skyway API-KEY
  - origin : your origin registered for API-KEY
  
* rpi-mqtt/conf/config.json

  - change URL of **mqtt-broaker**

* apply conf change

restart app by pm2

```bash
pm2 restart publisher
pm2 restart ssg
```

## trouble shoot

* raspberry PI

power off then on

* edge server

stop ifogcloud container then start
