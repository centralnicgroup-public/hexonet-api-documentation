# StatusObjectLog

## DESCRIPTION
Gives you detailed information on one specific object log entry.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusObjectLog` | COMMAND
LOGINDEX | 1 | ID of the logging entry | INT

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
506 | Invalid option value
507 | Invalid command format
510 | Command not supported for this class
530 | Authentication failed
531 | Authorization failed
532 | Domain names linked with name server
534 | Object has not been flagged for transfer
540 | Attribute value is not unique
541 | Invalid attribute value
543 | Final or implicit attribute cannot be updated
544 | Entity on hold
545 | Object not found
546 | Credit limit exceeded
547 | Invalid command sequence
548 | Object is not up for renewal
549 | Command failed
552 | Object status does not allow for operation
553 | Operation not allowed. Object pending transfer

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
LOGDATE | 1 | 1 | Date of the logging entry | DATETIME
LOGROLEID | 1 | 1 | Name of the role user who caused the log entry | TEXT or NULL
LOGSTATUS | 1 | 1 | Status of the logging entry, e. g. `ok` | TEXT
LOGUSER | 1 | 1 | Name of user who caused the log entry | TEXT
OBJECTCLASS | 1 | 1 | Object class | TEXT
OBJECTID | 1 | 1 | Object ID | TEXT
OPERATIONINFO[0..N] | 0 | N | The complete command and the response as text. Each array entry represents a line. | TEXT
OPERATIONSTATUS | 1 | 1 | Status of the operation | TEXT
OPERATIONTYPE | 1 | 1 | Type of the operation | TEXT
REFERENCE | 1 | 1 | Reference of the user who caused the log entry | TEXT
NEWOBJECTPROPERTIES[0..N] | 0 | N | The new properties of an object after e.g. an update | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusObjectLog
LOGINDEX = 31204904
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[LOGDATE][0] = 2016-11-12 21:58:04
PROPERTY[LOGROLEID][0] =
PROPERTY[LOGSTATUS][0] = ok
PROPERTY[LOGUSER][0] = test.user
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTID][0] = monzoncit.net
PROPERTY[OPERATIONINFO][0] = [HEADER]
PROPERTY[OPERATIONINFO][1] = user=test.user
PROPERTY[OPERATIONINFO][2] = remoteaddr=138.117.6.221:49607
PROPERTY[OPERATIONINFO][3] =
PROPERTY[OPERATIONINFO][4] = [COMMAND]
PROPERTY[OPERATIONINFO][5] = ORDER=CREATE
PROPERTY[OPERATIONINFO][6] = NAMESERVER1=ns2.ispapi.net
PROPERTY[OPERATIONINFO][7] = OWNERCONTACT0=USER
PROPERTY[OPERATIONINFO][8] = TECHCONTACT0=USER
PROPERTY[OPERATIONINFO][9] = INTERNALDNS=1
PROPERTY[OPERATIONINFO][10] = BILLINGCONTACT0=USER
PROPERTY[OPERATIONINFO][11] = COMMAND=AddDOMAIN
PROPERTY[OPERATIONINFO][12] = ADMINCONTACT0=USER
PROPERTY[OPERATIONINFO][13] = DOMAIN=monzoncit.net
PROPERTY[OPERATIONINFO][14] = PERIOD=1Y
PROPERTY[OPERATIONINFO][15] = NAMESERVER0=ns1.ispapi.net
PROPERTY[OPERATIONINFO][16] = EOF
PROPERTY[OPERATIONINFO][17] =
PROPERTY[OPERATIONINFO][18] = [RESPONSE]
PROPERTY[OPERATIONINFO][19] = PROPERTY[ORDERID][0]=34289
PROPERTY[OPERATIONINFO][20] = DESCRIPTION=Command completed successfully
PROPERTY[OPERATIONINFO][21] = CODE=200
PROPERTY[OPERATIONINFO][22] =
PROPERTY[OPERATIONINFO][23] = EOF
PROPERTY[OPERATIONSTATUS][0] = ORDER-CREATE
PROPERTY[OPERATIONTYPE][0] = CREATE
PROPERTY[REFERENCE][0] = test.user
EOF
```

----
