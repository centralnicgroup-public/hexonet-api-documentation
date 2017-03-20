# ResendDomainRegistrantVerificationEmail

## DESCRIPTION
Resends the registrant verification email for a specific domain.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ResendDomainRegistrantVerificationEmail` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500 | Invalid command name
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command failed
552 | Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ResendDomainRegistrantVerificationEmail
DOMAIN = reseller287.com
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
