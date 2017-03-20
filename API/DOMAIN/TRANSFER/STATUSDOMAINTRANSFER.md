# StatusDomainTransfer

## DESCRIPTION
This command returns various information about a pending transfer.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainTransfer` | COMMAND
DOMAIN | 1 | Name of the domain | DOMAIN

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
505 | Invalid attribute value syntax
530	| Authentication failed
531 | Authorization failed
540	| Attribute value is not unique
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
REPOSITORY | 1 | 1 | The repository in which the domain will be located after the transfer has been completed | TEXT
TRANSFERLOG[0..N] | 1 | N | The original log entries, separated by newlines | TEXT
TRANSFERSTATUS | 1 | 1 | Status, i.e. `PENDING` | TEXT
TRANSFERTYPE | 1 | 1 | The type of the transfer | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainTransfer
DOMAIN = hexonet-transfer.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[TRANSFERLOG][0] = 2016-09-26 15:46:44 [INITIATED] domain transfer initiated
PROPERTY[TRANSFERSTATUS][0] = INITIATED
PROPERTY[TRANSFERTYPE][0] = INCOMING
EOF
```

----
