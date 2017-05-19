# RequestDomainAuthInfo

## DESCRIPTION
This command allows to request an authorization code for a domain name transfer.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RequestDomainAuthInfo` | COMMAND
DOMAIN | 1 | Domain name | DOMAIN

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
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
541 | Invalid attribute value
545 | Object not found
549 | Command failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAIN | 1 | 1 | Domain name | TEXT
STATUS | 0 | 1 | Request status | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = RequestDomainAuthInfo
DOMAIN = testdomain.at
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; action pending
PENDING = 1
PROPERTY[DOMAIN][0] = testdomain.at
PROPERTY[STATUS][0] = PENDING
EOF
```

----
## NOTES

* This command is supported only for a few registries: CORE Association, DNS Belgium, nic.at and Norid.
