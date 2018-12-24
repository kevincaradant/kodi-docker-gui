# kodi-docker-gui
Runs kodi GUI from a docker container.   

## Building
```
docker build -t kodi-docker-gui.   
```


## First run
Prior first start, allow xhost:   
```bash   
DISPLAY=:0.0
export DISPLAY
xhost +local:docker   
```

## Docker Compose
Please check the `.env` file and change it at your conveniance   
Then: `docker-compose run kodi or docker-compose up`

## Command-line
```bash
docker run -i --device /dev/snd --device=/dev/dri -e DISPLAY -p $PORT:$PORT -v /run/dbus/:/run/dbus/:rw -v /dev/shm/:/dev/shm/:rw -v $HOST_PATH:/root/.kodi:rw -v /dev/lirc0:/dev/lirc0:rw -v /dev/lircd:/dev/lircd:rw -v /etc/group:/etc/group:ro -v /etc/passwd:/etc/passwd:ro -v /etc/shadow:/etc/shadow:ro -v /etc/sudoers.d:/etc/sudoers.d:ro -v /tmp/.X11-unix:/tmp/.X11-unix:rw kevin31/kodi-docker-gui   
```
Please check $PORT and $HOST_PATH
