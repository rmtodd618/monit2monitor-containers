docker-monit: very simple daemon that helps you monitor docker containers
by maintaining PID files for them.

Create file /etc/default/docker-monit with contents:

```
CONTAINERS="container1 container2 container3"
```

Then run from this git repo:

```
cp docker-monit /usr/local/bin/
cp docker-monit.conf /etc/init/
cp start-container /usr/local/bin
cp container.conf /etc/init/      Youll want to rename file to name of container and edit it to the name of container also ex:ui.conf



* you need to update conf.d/docker-monit and section /var/run/docker-monit/ with your container names filled in with names used above



Steps for having monit run out of the box

chmod 0700 monit/monitrc 

docker-compose up -d

docker exec monit_monit_1 monit status


http://admin:monit@IP:2812

cat /var/log/upstart/docker-monit.log to make sure if any errors of the 