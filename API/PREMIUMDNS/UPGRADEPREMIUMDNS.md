# UpgradePremiumDNS

## DESCRIPTION
Upgrade a PremiumDNS object to a higher class. There is a refund for the days that remain of the current validity period. The expiration date is reset according to the new validity period as provided in the command, but it may not be earlier than before the upgrade. If there was a prepayment for the PremiumDNS object, it is cancelled and refunded, too.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpgradePremiumDNS` | COMMAND
CLASS | 1 | New Premium DNS Product Class | `2M`, `5M`, `15M`, `30M`, `50M`, `75M`, `100M` or `ENTERPRISE`
OBJECTID | 1 | PremiumDNS object ID | TEXT
ORDER | 0 | PremiumDNS upgrade order action:<br>`CREATE` - create a PremiumDNS upgrade order<br>`REPLACE` - replace a PremiumDNS upgrade order<br>`UPDATE` - update a PremiumDNS upgrade order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | PremiumDNS upgrade order ID; only relevant if ORDER is `REPLACE` or `UPDATE` | INT
PERIOD | 0 | Validity period; the default is: `1Y` | PERIOD
RENEWALMODE | 0 | Renewal mode for the PremiumDNS object; possible values:<br>`AUTORENEW`<br>`AUTOEXPIRE`<br>If not specified, the renewal mode remains unchanged | `AUTORENEW` or `AUTOEXPIRE`

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
546 | Credit limit exceeded
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EXPIRATIONDATE | 1 | 1 | Expiration date of the PremiumDNS object | DATETIME
OBJECTID | 1 | 1 | PremiumDNS object ID | TEXT
STATUS | 1 | 1 | PremiumDNS object status | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = UpgradePremiumDNS
CLASS = 5M
OBJECTID = 4bf53dce-ba1f-479a-abf5-88481325a5ce
PERIOD = 3Y
RENEWALMODE = AUTORENEW
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EXPIRATIONDATE][0] = 2020-05-07 08:31:05
PROPERTY[OBJECTID][0] = 4bf53dce-ba1f-479a-abf5-88481325a5ce
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
