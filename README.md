# KeycloakOnDockerDocumentation
## Introduction
This is a brief documentation how to secure Frost servers with keycloak. To keep it simple, all examples are run in a docker container with the standard settings which are only changed when needed.
## Initzialize Keycloak
To setup Keycloak we use the offical docker image from their website.
´docker run -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:14.0.0´
This creates an admin user 'admin' with the password 'admin'. There are many other modifications that can be done rinning this container to learn maore about them vist https://www.keycloak.org/getting-started/getting-started-docker.
## Initialize a Frost Server
