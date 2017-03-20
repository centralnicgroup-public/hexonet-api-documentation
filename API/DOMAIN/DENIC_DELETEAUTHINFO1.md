# DENIC_DeleteAuthInfo1

## DESCRIPTION
You may use this command to delete an existing AuthInfo1 of a .DE domain.

## AVAILABILITY
All users have access to this command, but it applies only for .DE domains.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DENIC_DeleteAuthInfo1` | COMMAND
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
545 | Object not found
549 | Command failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
STATUS[0..N] | 1 | N | The status of the domain | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = DENIC_DeleteAuthInfo1
DOMAIN = mytestdomain1.de
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS][1] = clientTransferProhibited
EOF
```

----
