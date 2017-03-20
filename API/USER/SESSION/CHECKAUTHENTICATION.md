# CheckAuthentication

## DESCRIPTION
Authenticate a user against the system.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckAuthentication` | COMMAND
SUBUSER | 1 | ID of the account to authenicate (This can also be used by the user itself !) | TEXT
PASSWORD | 1 | Password of the user account | TEXT

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
QUOTA EXCEEDED | 0 | 1 | Returned with value "1" if quota exceeded | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckAuthentication
PASSWORD = 123456
SUBUSER = testuser1
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
