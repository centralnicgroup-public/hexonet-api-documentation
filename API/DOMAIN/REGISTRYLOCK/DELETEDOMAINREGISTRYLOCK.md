# DeleteDomainRegistrylock

## DESCRIPTION
Send an email to inform our team that our customer wants the registrylock removed.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteDomainRegistrylock` | COMMAND
DOMAIN | 1 | Name of the domain | DOMAIN

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteDomainRegistryLock
DOMAIN = hexonet.net
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; Our fulfillment team will initiate the removal of the Registry Lock
EOF
```

----
