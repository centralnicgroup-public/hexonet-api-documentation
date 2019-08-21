# RequestDomainPin

## DESCRIPTION
This command requests a TOKEN which must be used to authorize an update for a .BANK or .INSURANCE domain. The TOKEN will be sent to the registrant's email address

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RequestDomainPin` | COMMAND
DOMAIN | 1 | Domain name | DOMAIN

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
545 | Object not found
549 | Command failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = RequestDomainPin
DOMAIN = hexonet.bank
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; TOKEN requested
EOF
```

----
