# CheckNameserver

## DESCRIPTION
Check a nameserver host for availability.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckNameserver` | COMMAND
NAMESERVER | 1 | Name of the nameserver host | NAMESERVER
DOMAIN | 0 | Domain Name | DOMAIN or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
212 | Nameserver is available
213 | Nameserver is not available
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
507 | Invalid command format
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
REASON | 0 | 1 | Reason for non-availability of the nameserver | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckNameserver
NAMESERVER = ns187.hexonet.net
EOF
```
### Response

```
[RESPONSE]
CODE = 212
DESCRIPTION = Available
EOF
```

----
