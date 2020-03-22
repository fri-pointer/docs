# Security policy

This document specifies permissions, roles, keycloak configuration, etc.

## Provider

Planned provider for authentication is Keycloak server.
Security policy derives from its functionalities.

## Realm configuration

### Roles

Realm defines following roles:

#### admin role

Composite role, provides `admin` role in all clients.

#### user role

Composite role, provides `user` role in all clients.

### Users

#### Registration

Users are able to self-register, using Keycloak form,
or they can login through configured identity provider.

#### Login

Keycloak supports local strategy, but also provides list of identity providers.

##### Configured identity providers

- GitHub (already supported)
- Google (planned)
- Facebook (planned)

#### User attributes

Use of custom attributes is planned and will be managed with service account.
Proper mappers will be configured, so that those attributes are always present in token claim. 

##### mod_of

Attribute for programe moderators, professors and assitants. Provides array of
programe id's for which user has permission to moderate.
Attribute is meant to supplement specific role.

## Clients

### Backend service

| Key       | Value |
|-----------|-------|
| Client ID | backend-service |
| Type      | Confidential |
| Platform  | REST API |

#### Roles

Client provides a number of roles:

- user
- verified_user
- professor
- assistant
- program_mod
- global_mod
- admin

More in [Backend service page](./BACKEND_SERVICE.md).

### Web client

| Key       | Value |
|-----------|-------|
| Client ID | web-client |
| Type      | Public |
| Platform  | Web/HTML5 |

#### Roles

Client provides no additional roles.

More in [Web client page](./WEB_CLIENT.md).