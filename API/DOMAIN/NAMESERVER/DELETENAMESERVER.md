# DeleteNameserver

## DESCRIPTION
Deletes a Nameserver host in the registry.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteNameserver` | COMMAND
NAMESERVER | 1 | Name of the nameserver host | HOSTNAME
FORCE | 0 | Set to `1` to enforce the deletion of a nameserver object which is in use. <br> Please note that it is possible that domains which have the nameserver assigned will not resolve any longer. | `0` or `1`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423	| Command failed due to server error. Client should try again (Could not get session)
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
506	| Invalid option value
510	| Command not supported for this class
530 | Authentication failed
531	| Authorization failed
532	| Domain names linked with name server
541	| Invalid attribute value
545	| Object not found
549	| Command failed
552	| Object status does not allow for operation


No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteNameserver
NAMESERVER = ns186.hexonet.net
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
## NOTES

* The nameserver must not be linked with any domain name
