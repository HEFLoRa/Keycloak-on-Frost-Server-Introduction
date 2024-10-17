# Keycloak on Frost Server Introduction
## Preface

**IMPORTANT**: FROST-servers and Keycloak may work only when the url's are specified with a global IP or a domain-url - in other words: they don't communicate properly when hosted on localhost/127.0.0.1. 
**Both the serviceRootUrl and keycloakConfigUrl mustn't be specified using "localhost" or "127.0.0.1"!**

All exmaples are run with a docker-compose file. You can find seperate files for Keycloak and Frost or use the file in the *shared* folder which runs both services at once. To get no conflicts with different programs running locally on your machine make sure to check **docker container ls** and stop those containers.
A detailed description about docker-compose and all relevant comands can be found on https://docs.docker.com/get-started/

**It is recommended to individually set up the containters: first set up a Keycloak-instance, and then bind in one or several Frost-server-instances into the existing Keycloak-instance.**

## Set up Keycloak
Frist start the Keycloak server with said docker-compose file. The server runs on http://localhost:8080 . Now you can find the admin console of Keycloak in your webbrowser. To login use the user **admin** with the password **Pa55w0rd**. After you loged in you have to create a new client for the Frost server. To do this navigate to the realm **master** which should be already initialized and create a new client. 

To start said docker-compose file:
- go to the folder where the file is located on your machine
- once in the folder run `docker-compose up` or `docker-compose up *filename*` if there is more than one docker-compose in the folder
- After a few seconds you should be able to find the admin console on http://localhost:8080


![Keycloak-Clients](https://user-images.githubusercontent.com/43475725/125331575-72511900-e348-11eb-958a-f22bd8c5b394.png)

Click on create to create a new client.

![Keycloak-New-Client](https://user-images.githubusercontent.com/43475725/125332172-25ba0d80-e349-11eb-8438-8a3d77c67173.png)

Now there should a client for the Frost server. 

## Set up Frost
You can start the Frost server with the given docker-compose file (if you haven't done it alreday by using the shared docker-compose file) and connect its authorization to the Keycloak instance. You can access the frost server on http://<server-ip/url>:5000. For the exact commands go back to **Set up Keycloak**. This Frost server has no data in it. There is smaple data available on https://fraunhoferiosb.github.io/FROST-Server/deployment/docker.html which is easy to download.


## Alternative: shared option
There is another docker-compose file in the *shared* folder. This file allows you to both run the keycloak instance and the frost server with only one file. As there is a higher chance of conflicts on your local machine while running it this file is only for experienced developers who already know their way arround docker.
