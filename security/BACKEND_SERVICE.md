# Backend service security

## Type
Backend service is of confidential client type.
It is able to verify received token using public certificate and to
retrieve its own token. When service retrieves its own token it retrieves it
from service account using client id and client secret.

## Access
Backend service allows limited anonymous access, therefore it is not 
required that user is authenticated to access some parts 
of client. Most of the state-modifying endpoints are secured due to auditing, though.

## Roles

Backend service specifies a number of client roles that are 
used for fine-grained access to service endpoint:

- user
- verified_user
- professor
- assistant
- program_mod
- global_mod
- admin

### user

Default role that is granted upon registration. This is achieved by creating default group and granting the role to this group.
This role provides basic authenticated access for client.

### verified_user

Verified users have additional rights compared to regular users. Conditions for obtaining this role and privileges gained by this role will be defined later.

### professor

Alias role for `program_mod`

### Assistant

Alias role for `program_mod`

### program_mod

Role that is granted to user who will be moderating content for specified programe.
List of allowed programes is specified in attribute `mod_of` and is mapped to token.
Moderators can edit or remove content.

### global_mod
Similiar to programe moderator, except that they have a right to edit any programe.

### admin
General administrative role with all permissions.

## Mappers

Design of backend service does not foresee any additional mappers.
