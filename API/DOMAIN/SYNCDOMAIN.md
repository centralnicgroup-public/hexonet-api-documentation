# SyncDomain

## DESCRIPTION
By using this command, users with an own domain repository can synchronize the properties of a domain with the registry database, in case that the properties went out-of-sync.

## AVAILABILITY
This command is only available to users which hold their own domain repository.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `SyncDomain` | COMMAND
DOMAIN | 1 | Name of the domain | DOMAIN

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425	| Service temporarily locked; usage exceeded
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
507	| Invalid command format
521	| Too many sessions open. Server closing connection
530	| Authentication failed
531	| Authorization failed
540 | Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
547	| Invalid command sequence
549 | Command Failed
552	| Object status does not allow for operation

No properties are returned.
----
## Example

### Command

```
[COMMAND]
COMMAND = SyncDomain
DOMAIN = hexonet-domain.se
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
