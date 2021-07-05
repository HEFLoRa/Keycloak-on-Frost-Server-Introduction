# KeycloakOnDockerDocumentation
## Introduction
This is a brief documentation how to secure Frost servers with keycloak. To keep it simple, all examples are run in a docker container with the standard settings which are only changed when needed.
## Initzialize Keycloak
To setup Keycloak we use the offical docker image from their website.
`docker run -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:14.0.0`
This creates an admin user 'admin' with the password 'admin'. There are many other modifications that can be done running this container to learn maore about them vist https://www.keycloak.org/getting-started/getting-started-docker.
## Initialize a Frost Server
For the Frost Server we use a simple docker-compose file found on their website at https://fraunhoferiosb.github.io/FROST-Server/deployment/docker.html.
## Set up Keycloak
The docker image comes with a preinstalled master realm. Now you have to create a new client with the same root url as your Frost Server which is already running locally on your system. To avoid cors errors set the variable **web-origin** to *.
## Set up the Frost server
The standart settings in the docker-compose files are enough to get the basic features from keycloak. If more features are needed check out their documentation site at https://fraunhoferiosb.github.io/FROST-Server/settings/auth.html.
