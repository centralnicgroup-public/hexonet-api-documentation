# QueryObjectUserList

## DESCRIPTION
Queries users related to the objects specified in the command.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryObjectUserList` | COMMAND
LEVEL | 0 | `PEER` or `ENDUSER` (default) supplies either the user underneath the one who executed the command (peer) or the enduser related to the object (enduser) | `PEER` or `ENDUSER`
OBJECTCLASS | 0 | Filter output by a specific object class | TEXT
OBJECTID[0..N] | 1 | Object IDs for which the users should be queried | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
OBJECTID[0..N] | 1 | N | The respective user ID | TEXT
USER[0..N] | 1 | N | The respective user | TEXT or NULL

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryObjectUserList
LEVEL = ENDUSER
OBJECTCLASS = DOMAIN
OBJECTID0 = hexonet-domain.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[OBJECTID][0] = hexonet-domain.com
PROPERTY[USER][0] = subresell.com
EOF
```

----
