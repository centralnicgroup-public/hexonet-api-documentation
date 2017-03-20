# DeleteEvent

## DESCRIPTION
Delete an event.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteEvent` | COMMAND
EVENT | 1 | ID of the event | INT

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
541	| Invalid attribute value
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteEvent
EVENT = 22393711
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
