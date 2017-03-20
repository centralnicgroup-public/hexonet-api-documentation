# ApproveDomainRegistrantVerificationEmail

## DESCRIPTION
This command allows to approve a domain registrant verification email.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ApproveDomainRegistrantVerificationEmail` | COMMAND
TOKEN | 1 | Registrant verification token, received by email | TEXT

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
531 | Authorization failed
552 | Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ApproveDomainRegistrantVerificationEmail
TOKEN = E63B5003E996061C8A80B2765560C013-FC46E6C6890E02930F27413590BB474E
EOF
```
### Response

```
[RESPONSE]
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; Registrant has been verified
EOF
```

----
