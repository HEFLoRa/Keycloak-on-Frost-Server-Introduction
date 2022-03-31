## This compose-file starts FROST and Keycloak simulataneously.
It is however recommended to start them separately: 

1.) Frost-client first needs to be created in Keycloak 
2.) not every new frost-server requires a new keycloak-server - rather use existing one to bind in several frost-clients
