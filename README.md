# Quarkus Artemis Demo App

## Details
This is a simple DEMO app which based on quarkus. It opens HTTP socket from 8080 from path "/content/log" for clients. If any request receives, It sends the request's payload to Artemis. Also it receives all messages from Artemis every 10 seconds. It prints each message which received to console.

## Requirements before run locally
It may work wth older or newer versions but I did not tested.

- JDK 11
- Docker 19.03.0
- Maven 3.6.3
- docker-compose 3.8
- curl (only for test)

## Build --> Run --> Test

- before run the services we need to build the docker image

  > ./build_project.sh

- now we can run all services on docker-compose:

  > ./run.sh

- now we can test it

  > ./execute_http_request.sh

  Check "docker-compose" log. Maximum in 10 second you should see:
  
  > message (content data) received: I am the client
  
  text which is sent by http client. You can change this text from "execute_http_request.sh" file.
