# GetEnvironment

## DESCRIPTION
Query one or more environment values.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetEnvironment` | COMMAND
ENVIRONMENTKEY[0..N] | 0 | One or more keys of the environment names (prefixes of the name), e.g. `_system/defaults` | TEXT
ENVIRONMENTNAME[0..N] | 0 | One or more environment names (in the context of the environment key), e.g. `nameserver`, `renewalmode` or `language` | TEXT
LEVEL[0..N]  | 0 | Limit the number of parent user lookups to a dedicated number of levels. A value of e.g. `1` will only consider the direct parent user. This is e.g. useful if branding related environment values should have a default setting (defined by the direct parent user). In the case that a respective environment has not been set by the direct parant user the setting of his parent user will not be revealed | INT
SUBUSER[0..N] | 0 | One or more IDs of subuser account. If SUBUSER[X] is set for a dedicated environment query then USEPARENT[X] must not be requested for the same query | TEXT
USEPARENT[0..N] | 0 | Query environment values of parent users unless the environment is found. Starting from the user itself the environment value of the respective parent user will be searched as long as the evironment is not found. This way parent users can define a default setting which may be overwritten by there users and subusers. Environment settings of the parent user that have a PARENT_ONLY_READABLE flag set can not be queried. It is possible to restrict the number of searched levels with the LEVEL[0..N] parameter. If USEPARENT[X] is set for a dedicated environment query it must not be combined with SUBUSER[X] | `0` or `1`

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
531 | Authorization failed
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ENVIRONMENTVALUE[0..N] | 1 | N | Environment value | TEXT
INVALID[0..N] | 0 | N | Invalid environments; only present if any environment queries failed | TEXT or NULL
MISSING[0..N] | 0 | N | Missing environments; only present if any environment queries failed | TEXT or NULL
PARENT_ONLY_READABLE[0..N] | 0 | N | Indicates if the environment is only readable by the parent user. If the parameter SUBUSER[X] is not given this property will always be empty | INT or NULL
PARENT_ONLY_WRITABLE[0..N] | 0 | N | Indicates if the environment is only writable by the parent user. If the parameter SUBUSER[X] is not given this property will always be empty | INT or NULL
PRIVATE[0..N] | 0 | N | Indicates if a value is hidden from subusers | INT or NULL

----
## Example

### Command

```
[COMMAND]
COMMAND = GetEnvironment
ENVIRONMENTKEY0 = _system/defaults
ENVIRONMENTKEY1 = _system/defaults
ENVIRONMENTNAME0 = nameserver
ENVIRONMENTNAME1 = renewalmode
SUBUSER0 = test.customer
SUBUSER1 = test.customer
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ENVIRONMENTVALUE][0] = ns1.hexonet.net,ns2.hexonet.net
PROPERTY[ENVIRONMENTVALUE][1] =
PROPERTY[MISSING][0] = _system/defaults/renewalmode
PROPERTY[PARENT_ONLY_READABLE][0] = no
PROPERTY[PARENT_ONLY_READABLE][1] =
PROPERTY[PARENT_ONLY_WRITABLE][0] = no
PROPERTY[PARENT_ONLY_WRITABLE][1] =
PROPERTY[PRIVATE][0] = 0
PROPERTY[PRIVATE][1] =
EOF
```

----
