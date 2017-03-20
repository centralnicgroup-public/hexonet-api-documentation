# CancelDomainRegistration

## DESCRIPTION
This command allows to cancel a domain name registration.

## AVAILABILITY
Only for registrars using our RegistrarOC system.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CancelDomainRegistration` | COMMAND
DOMAIN | 1 | Domain name | DOMAIN
REASON | 0 | Cancellation reason | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
545 | Object not found
552 | Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = CancelDomainRegistration
DOMAIN = test-domain.it
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
EOF
```

----
## NOTES

* This command is applicable only to domain names, which are in a pending state after the creation.
