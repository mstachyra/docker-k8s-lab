# Notes

1. Run with default config
2. Create user
3. Deploy config `\\wsl.localhost\docker-desktop-data\data\docker\volumes\....`
4. Restart
5. Look at te log

https://hub.docker.com/_/eclipse-mosquitto/

``` bash
docker run -it -p 1883:1883 -p 9001:9001 -v ~/docker/mosquitto:/mosquitto --name mytest eclipse-mosquitto
docker exec -it mosquitto sh
/mosquitto/config/

create file "pass" into config folder
# https://mosquitto.org/man/mosquitto_passwd-1.html
cp ~/docker/temp/mosquitto.conf ~/docker/mosquitto/config/
cp /home/mstac/docker/temp/mosquitto.conf /home/mstac/docker/mosquitto/config -f
```

Create user -> call this inside container. File `/mosquitto/config/pass` will be stored 
``` sh
mosquitto_passwd -c /mosquitto/config/pass mstachyra
```
