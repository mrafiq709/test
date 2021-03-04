# test

MongoDb settings for windows:
-----------------------------
1. Go to
```
laradock
   |_docker-compose.yml
```
and find below code portion and update like this
```
### MongoDB ##############################################
    mongo:
      build: ./mongo
      restart: always
      ports:
        - "${MONGODB_PORT}:27017"
      volumes:
        #- ${DATA_PATH_HOST}/mongo:/data/db
        #- ${DATA_PATH_HOST}/mongo_config:/data/configdb
        - "/${USER}/${MONGO_SAVE_PATH}:/data/db"
      networks:
        - backend
```
2. Go to
```
laradock
   |_.env
```
and add below code
```
MONGO_SAVE_PATH=./laradock/data
USER=your_user_name # you can find your user name by typing ***whoami*** in command
```

