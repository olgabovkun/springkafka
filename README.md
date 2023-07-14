# Creating Kafka cluster using Docker Compose and uses Spring Kafka to send and receive data from topics

This project consists of two modules ms-consumer and ms-producer which can be started on port 8082 and 8083. (Here is an example of [creating Gradle multi-module project](https://github.com/orb48/multimodule))

## Requirements
* Java 17  
* Spring  
* Docker  

## Creating kafka cluster docker-compose file
Docker Compose uses the Compose file format to running multi-container applications on Docker.  With a Compose file, the application can be created and started with a single command, `docker compose up`.

**Step 1.** Install docker https://docs.docker.com/get-docker/  
**Step 2.** `cd config/env`  
**Step 3.** Create docker containers using `docker compose up -d` (-d flag runs in the background and lets you access the terminal after starting)  
**Step 4.** You are ready to work with kafka!  
  
**Step last.** Stop app `docker compose down`  

## Send data
To send data you need to start modules ms-consumer, ms-producer on port 8082 and 8083.  
Using curl send request to topic:  

`curl --location 'http://localhost:8083/api/v1/producer/send-message' \
--header 'Content-Type: application/json' \
--data '{
    "message": "any message"
}'`
