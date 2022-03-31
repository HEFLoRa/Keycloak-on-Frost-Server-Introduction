Hints:

- When FROST shall be protected by Keycloak avoid specifying "localhost" for both URL-fields in the compose file
- Secret must be taken from keycloak-client 
- Never change the internal ports (the ones on the right side of the ":"), only the external ones > pay attention that external ports are unique on the same server
