# QueryEnvironmentList

## DESCRIPTION
Query the list of environment keys or query all name-value pairs for an environment key.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryEnvironmentList` | COMMAND
ENVIRONMENTKEY | 0 | Key of the environment | TEXT
SUBUSER | 0 | ID of the subuser account | TEXT or NULL
MATCHMODE | 0 | Must be either `EXACT` or `PREFIX`. Default is `EXACT`.<br> If set to `EXACT` only environment values will be returned where the ENVIRONMENTKEY stated in the command matches exactly.<br>If set to `PREFIX` the environment values will be returned where the ENVIRONMENTKEY stated in the command matches as a prefix. | TEXT or NULL

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


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
TOTAL | 1 | 1 | The total number of entries found | INT
ENVIRONMENTKEY[0..N] | 0 | N | Environment key | TEXT
ENVIRONMENTNAME[0..N] | 0 | N | Environment name | TEXT
ENVIRONMENTVALUE[0..N] | 0 | N | Value of the environmentkey/name | TEXT
PARENT_ONLY_READABLE[0..N] | 0 | N | Only returned if subuser parameter is stated in the command. Indicates if an environment value is only readable by the parent user | TEXT
PARENT_ONLY_WRITABLE[0..N] | 0 | N | Only returned if subuser parameter is stated in the command. Indicates if an environment value is only writable by the parent user | TEXT
PRIVATE[0..N] | 0 | N | Flag, which shows if the respective value is hidden from the subusers | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryEnvironmentList
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 12
PROPERTY[COUNT][0] = 13
PROPERTY[TOTAL][0] = 13
PROPERTY[ENVIRONMENTKEY][0] = invoice
PROPERTY[ENVIRONMENTKEY][1] = invoice/config/en
PROPERTY[ENVIRONMENTKEY][2] = invoice_config/en
PROPERTY[ENVIRONMENTKEY][3] = user-info/contact/company
PROPERTY[ENVIRONMENTKEY][4] = _system/command/setdomainrenewalmode
PROPERTY[ENVIRONMENTKEY][5] = _system/contact
PROPERTY[ENVIRONMENTKEY][6] = _system/defaults
PROPERTY[ENVIRONMENTKEY][7] = _system/defaults/renewalmode/domain
PROPERTY[ENVIRONMENTKEY][8] = _system/wdrp
PROPERTY[ENVIRONMENTKEY][9] = _system/whois
PROPERTY[ENVIRONMENTKEY][10] = _wi/template/default
PROPERTY[ENVIRONMENTKEY][11] = _wi2/template/default
PROPERTY[ENVIRONMENTKEY][12] = _wi2/template/test
EOF
```

----
## Notes

* If ENVIRONMENTKEY is defined, then the request returns all name/value pairs for this key.
* If ENVIRONMENTKEY is undefined, then the request returns all environmentkeys.
