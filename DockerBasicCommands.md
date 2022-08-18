# Docker Basic Commands

## pull image from docker hub to local:
```
docker pull <<image-name>>
```

## list all the images:
```
docker image
```

## run the container with specific image in detached/backgound mode:
```
docker run -d <<image-name>>
docker run -d -p<<local-port>>:<<container-port>> <<image-name>>
```

## List all the running containers:
```
docker ps-a
```

## Start/Stop container:
```
docker start <<container-id/container-name>>
docker stop <<container-id/container-name>>
```

## delete docker image or container:
```
docker rm <<container-name/id>>
docker rmi <<image-name/id>>
```

## check log of running container:
```
docker logs <<container-name/id>>
docker logs <<container-name/id>> | tail
```

## dommand to go inside container ininteractive mode:
```
docker exec -it <<container-id/name>> /bin/bash
docker exec -it <<container-id/name>> /bin/sh
```

## Docker docker network
```
docker network create <<network-name>>
docker network ls
```

## Docker run command to start MongoDB container:
```
docker run -d \
--net mongo-network \
--name mongodb-01 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=admin \
mongo
```
```
docker run -d --net mongo-network --name mongodb-01 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin mongo
```

## Docker run command to start MongoDB-express container:
```
docker run -d \
--net mongo-network \
--name mongodb-exp-01 \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_SERVER=mongodb-01 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=admin \
mongo-express
```
```
docker run -d --net mongo-network --name mongodb-exp-01 -p 8081:8081 -e ME_CONFIG_MONGODB_SERVER=mongodb-01 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=admin mongo-express
```


## Docker compose commands:
```
docker-compose -f <<.yml/.yaml file name>> up
docker-compose -f <<.yml/.yaml file name>> down
```


## Docker command to build an image from scratch to your local machine:
```
docker build -t <<my-app>>:<<tag-version>> .
```


## Docker tag command (rename)
```
docker tag <<my-image>>:<<my-tag>> <<AWS ECR URL>>:<<tag>>
```

## Push that image to AWS
```
docker push <<AWS ECR URL>>:<<tag>>
```

