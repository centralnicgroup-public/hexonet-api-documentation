# DENIC_CreateAuthInfo2

## DESCRIPTION
This command is used to let the DENIC generate the AuthInfo2 for a .DE domain.

## AVAILABILITY
All users have access to this command, but it applies only for .DE domains.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DENIC_CreateAuthInfo2` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN

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
541 | Invalid attribute value
546 | Credit limit exceeded
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DENIC_CreateAuthInfo2
DOMAIN = mytestdomain1.de
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
