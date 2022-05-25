ESPHome project on balena

![](https://raw.githubusercontent.com/iayanpahwa/esphome-app/master/assets/logo.png)
--------------------

## Introduction

ESPHome is a system to control your ESP8266/ESP32 by simple yet powerful configuration files and control them remotely through Home Automation systems.
--------------------
## Hardware required

- A Single board computer like Raspberry Pi 4 -- currently tested to work
- SD card ex 16GB Micro-SD Card depending upon the board type
- Power supply for the board

--------------------
## Deploy 

- To use standalone clone this repo and use [balena push](https://www.balena.io/docs/learn/deploy/deployment/#balena-push)

- Deploy directly from here 👇🏻

[![deploy button](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/iayanpahwa/esphome-app)


- To use in a multi-container app, add following in your docker-compose file

```
version: '2.1'

volumes:
    config:
services:
  esphome:
    container_name: esphome
    image: esphome/esphome
    ports:
      - '6052:6052'
    volumes:
      - 'config:/config'
    restart: unless-stopped
    privileged: true
    network_mode: host
 ``` 
---------
## Usage 

Once the app is deployed, head over to the URL of your device port number ```<Device_IP>:6052``` 6052 is default port of ESPHome
---------
## Attribution

* [ESPHome](http://esphome.io)