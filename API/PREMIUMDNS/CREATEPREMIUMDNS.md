# CreatePremiumDNS

## DESCRIPTION
Purchase a PremiumDNS product for a certain DNS zone.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreatePremiumDNS` | COMMAND
CLASS | 1 | Premium DNS Product Class | `2M`, `5M`, `15M`, `30M`, `50M`, `75M`, `100M` or `ENTERPRISE`
DNSZONE | 1 | DNS zone for which the PremiumDNS product is purchased | TEXT
ORDER | 0 | PremiumDNS order action:<br>`CREATE` - create a PremiumDNS order<br>`REPLACE` - replace a PremiumDNS order<br>`UPDATE` - update a PremiumDNS order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | PremiumDNS order ID; only relevant if ORDER is `REPLACE` or `UPDATE` | INT
PERIOD | 0 | Validity period; the default is: `1Y` | PERIOD
RENEWALMODE | 0 | Renewal mode for the PremiumDNS product; possible values:<br>`AUTORENEW`<br>`AUTOEXPIRE`<br>If not specified, the user's default renewal mode will be used | `AUTORENEW` or `AUTOEXPIRE`
INTERNALDNS | 0 | Creates the necessary dns zone before submitting application to the registry. | `0`, `1` or NULL

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
546 | Credit limit exceeded

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
COMMAND = CreatePremiumDNS
CLASS = 2M
DNSZONE = example.zone.      
PERIOD = 2Y
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EXPIRATIONDATE][0] = 2019-05-08 08:20:09
PROPERTY[OBJECTID][0] = 4bf53dce-ba1f-479a-abf5-88481325a5ce
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
