docker-kimai
A docker image for Kimai time tracking based on the official php docker image.

This repository also contains a docker-compose.yaml configuration file for simple usage together with the official mariadb image.

Supported tags and respective Dockerfile links
1.1.0, stable, latest (Dockerfile)
Getting started
Make sure you have current versions of Docker (>= 1.12) and docker-compose (>= 1.9).
Clone this repository
Create a docker volume named kimai-database:
$ docker volume create --name kimai-database
Create and start the docker containers using docker-compose:
$ docker-compose up
This will command will:

Fetch the necessary docker images
Start the Apache and Mariadb services
After completion, you should be able to access the Kimai instance at http://localhost:8080 and peform the initial installation. For the database connection choose the following parameters:

Host: db
User: kimai
Password: kimai
Database: kimai (Existing)
After you finished the installation, you should remove the installer directory:

docker-compose exec kimai rm -rf /var/www/html/installer
Configuration
Create a file .env in the working directory with any of the following variables:

EXTERNAL_PORT: The external port (and ip address) to bind to (default 127.0.0.1:8080)
