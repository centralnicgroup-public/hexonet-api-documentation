# ExecuteOrder

## DESCRIPTION
This command allows to execute an order.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ExecuteOrder` | COMMAND
ORDERID | 1 | Order ID | INT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
500 | Invalid command name
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
506 | Invalid option value
507 | Invalid command format
510 | Command not supported for this class
520 | Server closing connection. Client should try opening new connection
530 | Authentication failed
531 | Authorization failed
532 | Domain names linked with name server
534 | Object has not been flagged for transfer
536 | Object already flagged for transfer
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
546 | Credit limit exceeded
547 | Invalid command sequence
548 | Object is not up for renewal
549 | Command failed
552 | Object status does not allow for operation
555 | Object already renewed

The command returns response properties, according to the results of the order execution.

----
## Example

### Command

```
[COMMAND]
COMMAND = ExecuteOrder
ORDERID = 34319
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-11-15 15:29:06
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
## NOTES

* An order can be executed only if it is in the `PENDING` state and its processing status is `INACTIVE`.
