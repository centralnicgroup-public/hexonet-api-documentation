# DeleteDomain

## DESCRIPTION
Delete a domain name.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
X-AT-SCHEDULEDATE | 0 | Only for .AT: In order to schedule the deletion at the registry for the end of the term of the domain use `expiration` and for immediate deletion use `now`; default value: `expiration` | TEXT or NULL

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
504	| Missing required attribute
505 | Invalid attribute value syntax
506	| Invalid option value
507	| Invalid command format
521	| Too many sessions open. Server closing connection
530 | Authentication failed
531 | Authorization failed
532	| Domain names linked with name server
541 | Invalid attribute value
544	| Entity on hold
545	| Object not found
547	| Invalid command sequence
549 | Command Failed
552	| Object status does not allow for operation
553	| Operation not allowed. Object pending transfer

NOTE: The response might include the parameter 'PENDING = 1'. In case of domain deletions this indicates that the deletion is pending and a restore of the domain might still be possible.

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
STATUS | 0 | 1 | The new status of the domain | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteDomain
DOMAIN = hexonerd.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; action pending
PENDING = 1
PROPERTY[STATUS][0] = PENDINGDELETE
EOF
```

----
