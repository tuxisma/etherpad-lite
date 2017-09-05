# etherpad-lite
A repo about etherpad running on Debian/Ubuntu. 

I've created a image about Etherpad hosted on (https://hub.docker.com/r/tuxisma/eptlacuaches/) so you can download and use the image in order to deploy it on a container using Docker.

This project has been inspired by Tlacuaches Project so feel free to contribute and try it.

![alt text](http://i.imgur.com/zYrGkg3.gif "Etherpad in action on PrimaryPad")



## Quickstart

### Step 1

#### Run a container MySQL

```sh
$ docker network create tlacuaches_network
$ docker run -d --network tlacuaches_network -e MYSQL_ROOT_PASSWORD=password --name tlacuachesdb mysql
```

### Step 2

Start an instance of Etherpad Lite:

```sh
$ docker run -d \
    --network tlacuaches_network \
    -e ETHERPAD_DB_HOST=tlacuachesdb \
    -e ETHERPAD_DB_PASSWORD=password \
    -p 9001:9001 \
    tuxisma/eptlacuaches
```


Access Etherpad from http://localhost:9001/
Etherpad will automatically create an etherpad database in the specified mysql server if it does not already exist. 

See the next environment variables in order to understand how the image works:


