# StatusEvent

## DESCRIPTION
Query an event.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusEvent` | COMMAND
EVENT | 1 | ID of the event | INT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530	| Authentication failed
531 | Authorization failed
545	| Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CLASS | 1 | 1 | Class of the event | TEXT
DATA[0..N] | 1 | N | Data of the event | TEXT
DATE | 1 | 1 | Creation date of the event | TEXT
INFO | 0 | 1 | Additional url encoded debug info | TEXT
SUBCLASS | 1 | 1 | Subclass of the event | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusEvent
EVENT = 22473397
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CLASS][0] = DOMAIN_TRANSFER
PROPERTY[DATA][0] = domain:usertransferperiodtest.ag
PROPERTY[DATE][0] = 2016-10-17 08:27:40.0
PROPERTY[INFO][0] = USERTRANSFER%3a%20dasc%20%2d%3e%20test%2euser
PROPERTY[SUBCLASS][0] = TRANSFER_PENDING
EOF
```

----
