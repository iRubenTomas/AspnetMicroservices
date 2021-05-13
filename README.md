# AspnetMicroservices
AspnetMicroservices

#Setting Docker compose in a solution
-Right click on the solution
-Click "Add Container Orchestrator Support"

Dockerfile is compose by two parts: building and running

Defining volumes for persisting database;
Volumes are basically data storage outside the coitainers and exist on the host file system which means if we remove the container with Mongo image the records will be safe

To run the docker compose:
docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d

To stop all containers:
docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml down

Docker debuging:
docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d

docker ps -aq

(Stop all the cotainers running on my machine)
docker stop $(docker stop -aq)

(Delete all the cotainers running on my machine)
docker rm $(docker ps -aq)

(Delete all the images running on my machine)
docker rmi $(docker images ps -q)

(Check logs)
docker logs -f aspnetrun-redis

(To execute commands inside of a container)
docker exec -it aspnetrun-redis /bin/bash

#Redis
(To execute redis commands)
redis-cli 

set key

get Key

Through Redis we will save the basket from each user where the key is the username and the value will be a json object containing all the prodcuts inside the user's basket