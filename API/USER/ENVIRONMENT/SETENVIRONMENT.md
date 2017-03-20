# SetEnvironment

## DESCRIPTION
Set an environment value.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `SetEnvironment` | COMMAND
ENVIRONMENTKEY | 0 | Key of the environment name (prefix of the name) | TEXT
ENVIRONMENTNAME | 1 | Name of the environment value | TEXT
ENVIRONMENTVALUE | 0 | Value of the environmentkey/name. If not passed the environment will be deleted | LONGTEXT or NULL
ENVIRONMENTKEY[0..N] | 0 | Key of the environment name (prefix of the name) | TEXT
ENVIRONMENTNAME[0..N] | 0 | Name of the environment value | TEXT
ENVIRONMENTVALUE[0..N] | 0 | Value of the environmentkey/name. If not passed the environment will be deleted | LONGTEXT or NULL
PRIVATE[0..N] | 0 | Flag, which shows if the respective value is hidden from the subusers | `0`, `1` or NULL
SUBUSER | 0 | ID of the subuser account | TEXT or NULL
PRIVATE | 0 | Flag, which shows if the respective value is hidden from the subusers | `0`, `1` or NULL
PARENTONLYWRITABLE | 0 | If set to `YES` only the subuser's partentuser has write access to the environment | `YES`, `NO` or NULL
PARENTONLYREADABLE | 0 | If set to `YES` only the subuser's partentuser has read access to the environment | `YES`, `NO` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531	| Authorization failed
541 | Invalid attribute value
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = SetEnvironment
ENVIRONMENTKEY = _system/defaults
ENVIRONMENTNAME = nameserver
ENVIRONMENTVALUE = ns1.hexonet.net,ns2.hexonet.net
SUBUSER = test.customer
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
