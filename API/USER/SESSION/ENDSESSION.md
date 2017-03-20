# EndSession

## DESCRIPTION
Ends the current session.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `EndSession` | COMMAND

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
421 | Command failed due to server error. Client should try again
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531	| Authorization failed
545	| Object not found
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = EndSession
EOF
```
### Response

```
[RESPONSE]
CODE=200
DESCRIPTION = Command completed successfully
EOF
```

----
