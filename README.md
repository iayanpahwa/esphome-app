# esphome-app
ESPhome project on balena
---------
## Usage 

- To use standalone clone this repo and use [balena push](https://www.balena.io/docs/learn/deploy/deployment/#balena-push)

- To use in a multi-container app, add following in your docker-compose file

```
version: '2.1'

volumes:
    data:
services:
  esphome:
    container_name: esphome
    image: esphome/esphome
    ports:
      - '6052:6052'
    volumes:
      - 'data:/config'
    restart: unless-stopped
    privileged: true
    network_mode: host
 ``` 
---------
## Attribution

* [ESPhome](http://esphome.io)