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
ADMINCONTACT | 0 | 1 | The admin contact stated in the transfer request | TEXT
BILLINGCONTACT | 0 | 1 | The billing contact stated in the transfer request | TEXT
CREATEDDATE | 1 | 1 | Creation date of the transfer | DATETIME
OLD-REGISTRAR | 0 | 1 | The sponsoring registrar at the time of the transfer initiation | TEXT
OWNERCONTACT | 0 | 1 | The owner contact stated in the transfer request | TEXT
REPOSITORY | 1 | 1 | The repository in which the domain will be located after the transfer has been completed | TEXT
TECHCONTACT | 0 | 1 | The technical contact stated in the transfer request | TEXT
TRANSFERLOG[0..N] | 1 | N | The original log entries, separated by newlines | TEXT
TRANSFERSTATUS | 1 | 1 | Status, i.e. `PENDING` | TEXT
TRANSFERTYPE | 1 | 1 | The type of the transfer | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the transfer | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainTransfer
DOMAIN = transfer-hexonet.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2017-03-27 12:22:04
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[TRANSFERLOG][0] = 2017-03-27 12:22:04 [INITIATED] domain transfer initiated
PROPERTY[TRANSFERSTATUS][0] = INITIATED
PROPERTY[TRANSFERTYPE][0] = INCOMING
PROPERTY[UPDATEDDATE][0] = 2017-03-27 12:22:04
EOF
```

----
