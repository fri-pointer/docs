# Security policy

This document specifies permissions, roles, keycloak configuration, etc.

## Clients

### Backend service

| Key       | Value |
|-----------|-------|
| Client ID | backend-service |
| Type      | Confidential |

#### Roles

Client provides a number of roles:

- user
- verifier_user
- professor
- assistant
- program_mod
- global_mod
- admin


### Web client

| Key       | Value |
|-----------|-------|
| Client ID | web-client |
| Type      | Public |

#### Roles

Client provides no additional roles