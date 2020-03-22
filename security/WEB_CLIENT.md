# Web client security


## Type
Web client is HTML5 application and therefore unsecure.
Client type for such applications is public. 
They are not able to retrieve their own token,
so they rely on redirecting user to Keycloak's login page for credentials.


## Access
Web client allows anonymous access, therefore it is not 
required that user is authenticated to access some parts 
of client.

## Roles

Web client provides no role of its own. Instead it relies on roles from `backend service`.

## Mappers

Web client provides mapper that maps user attribute `mod_of` to token claim.
