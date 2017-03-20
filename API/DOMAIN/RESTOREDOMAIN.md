# RestoreDomain

## DESCRIPTION
The RestoreDomain command automatically request a restore at the respective registry. The processing depends on the respective TLD/ccTLD / registry and varies from realtime up to 3 working days.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RestoreDomain` | COMMAND
DOMAIN | 1 | Domain Name | TEXT
RENEWALMODE | 0 | The renewal mode of the domain after it has been restored | NULL or TEXT
SUBUSER | 0 | The account in which the domain will be located after the restore | TEXT
CLASS | 0 | To restore e.g. a premium domain name, the domain CLASS needs to be provided | TEXT
ORDER | 0 | Order action:<br>`CREATE` - create a restore order<br>`REPLACE` - replace a restore order<br>`UPDATE` - update a restore order | `CREATE`, `REPLACE` or `UPDATE`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500 | Invalid command name
502	| Invalid entity value
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
507	| Invalid command format
510	| Command not supported for this class
530 | Authentication failed
531	| Authorization failed
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
548	| Object is not up for renewal
549 | Command Failed
552	| Object status does not allow for operation
554	| Object already registered

NOTE: A successful response will include the parameter 'PENDING = 1' which indicates that the restore has been requested and that an event will be created at a later point in time to notify about the outcome of the operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAIN | 0 | 1 | The domain name of the command (only present if returned by the respective registry) | DOMAIN
EXPIRATIONDATE | 0 | 1 | The new expiration date of the domain (only present if returned by the respective registry) | DATETIME
----
## Example

### Command

```
[COMMAND]
COMMAND = RestoreDomain
DOMAIN = hexonerd.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PENDING = 1
EOF
```

----
