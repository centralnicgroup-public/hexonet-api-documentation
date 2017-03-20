# PushDomain

## DESCRIPTION
With this command a domain can be pushed to the registry or to another registrar. This feature currently works for .DE domains ([DENIC Transit](https://transit.denic.de)), .UK domains (.UK detagging), .VE domains, .IS domains and .AT domains (.AT Billwithdraw).

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `PushDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
TARGET | 0 | Target, default: `TRANSIT` | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505	| Invalid attribute value syntax
507	| Invalid command format
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
549 | Command Failed
552	| Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = PushDomain
DOMAIN = my-domain.de
TARGET = TRANSIT
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
