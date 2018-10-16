# SetPremiumDNSRenewalMode

## DESCRIPTION
Set the renewal mode of a PremiumDNS object. The renewal mode determines whether the PremiumDNS object is renewed at the end of its validity period or not.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `SetPremiumDNSRenewalMode` | COMMAND
OBJECTID | 1 | PremiumDNS object ID | TEXT
RENEWALMODE | 1 | Renewal mode for the PremiumDNS object; possible values:<br>`AUTORENEW`<br>`AUTOEXPIRE` | `AUTORENEW` or `AUTOEXPIRE`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = SetPremiumDNSRenewalMode
OBJECTID = 02009f45-cc5c-424c-86d1-bd1cbe345451
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
