#Software
Docker Desktop
Docker Toolbox

#Docker Toolbox includes the following Docker tools:
Docker CLI client for running Docker Engine to create images and containers
Docker Machine so you can run Docker Engine commands from Windows terminals
Docker Compose for running the docker-compose command
Kitematic, the Docker GUI
Docker QuickStart shell preconfigured for a Docker command-line environment
Oracle VM VirtualBox

#DOCKER POSTGRES
#create postgres docker container
docker pull postgres
docker run --name dockerpostgres -e POSTGRES_PASSWORD=pass -d postgres
docker run --name dockerpostgres1 -e POSTGRES_PASSWORD=pass -d postgres

#connect
$ docker exec -it dockerpostgres psql -U postgres
$ docker exec -it dockerpostgres1 psql -U postgres

#run queries
CREATE DATABASE testdb
Switch connection to a new database
\c testdb

\! clear

--postgre syntax : (user not allowed as table name) 
CREATE TABLE users(
 id serial PRIMARY KEY,
 email VARCHAR (50) UNIQUE NOT NULL,
 first_name VARCHAR (50),
 last_name VARCHAR (50)
);

select * from users;

INSERT INTO users(
	id, email, first_name, last_name)
	VALUES (1, 'e@e.com', 'fn' , 'ln');
	
	INSERT INTO users(
	email, first_name, last_name)
	VALUES ('e1@e1.com', 'fn' , 'ln');
	
ctrl + z to exit psql

#remove docker container
docker container rm dockerpostgres
docker stop postgres

#docker commands
docker start – Starts one or more stopped containers
docker stop – Stops one or more running containers

docker stop dockerpostgres
docker start dockerpostgres

get full id of container
docker ps -q --no-trunc

help on docker command
docker ps --help