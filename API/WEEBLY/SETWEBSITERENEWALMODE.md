# SetWebsiteRenewalMode

## DESCRIPTION
Set the renewal mode of a WEBSITE object. The renewal mode determines whether the WEBSITE object is renewed at the end of its validity period or not.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `SetWebsiteRenewalMode` | COMMAND
ID | 1 | WEBSITE object ID | INT
RENEWALMODE | 1 | Renewal mode for the WEBSITE object; possible values:<br>`AUTORENEW`<br>`AUTOEXPIRE` | `AUTORENEW` or `AUTOEXPIRE`

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

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = SetWebsiteRenewalMode
OBJECTID = 264287657782855697
RENEWALMODE = AUTOEXPIRE
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
