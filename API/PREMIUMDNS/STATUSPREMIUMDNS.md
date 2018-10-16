# StatusPremiumDNS

## DESCRIPTION
Query the status of a PremiumDNS object.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusPremiumDNS` | COMMAND
OBJECTID | 1 | PremiumDNS object ID | TEXT

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACCOUNTINGDATE | 1 | 1 | Accounting date of the PremiumDNS object | DATETIME
ACCOUNTINGPERIOD | 1 | 1 | Accounting period of the PremiumDNS object | PERIOD
CLASS | 1 | 1 | Class of the object: `PREMIUMDNS` | TEXT
CREATEDDATE | 1 | 1 | Creation date of the PremiumDNS object | DATETIME
DESCRIPTION | 1 | 1 | DNS zone of the PremiumDNS object in unicode | TEXT
DNSZONE | 1 | 1 | DNS zone of the PremiumDNS object | TEXT
EXPIRATIONDATE | 1 | 1 | Expiration date of the PremiumDNS object | DATETIME
FAILUREDATE | 1 | 1 | Failure date of the PremiumDNS object | DATETIME
FAILUREPERIOD | 1 | 1 | Failure period of the PremiumDNS object | PERIOD
FINALIZATIONDATE | 1 | 1 | Finalization date of the PremiumDNS object | DATETIME
FINALIZATIONPERIOD | 1 | 1 | Finalization period of the PremiumDNS object | PERIOD
NEXTACTION | 1 | 1 | Defines the next action that will be performed on the PremiumDNS object. It can be:<br>`pay`: A payment from the respective user account will be charged.<br>`finalize`: The renewal of the PremiumDNS object is finalized.<br>`expire`: The PremiumDNS object is not renewed as per object renewal mode setting.<br>`expireunpaid`: The PremiumDNS object is not renewed because there is not enough money on the user account to pay for the renewal. | TEXT
NEXTACTIONDATE | 1 | 1 | The date when the next action will be taken | DATETIME
OBJECTID | 1 | 1 | PremiumDNS object ID | TEXT
PAIDUNTILDATE | 1 | 1 | Paid until date of the PremiumDNS object | DATETIME
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PREPAIDPERIOD | 1 | 1 | Prepaid period of the PremiumDNS object | PERIOD
RENEWALMODE | 1 | 1 | Renewal mode of the PremiumDNS object.<br> Can be `AUTORENEW` or `AUTOEXPIRE` | `AUTORENEW` or `AUTOEXPIRE`
STATUS | 1 | 1 | PremiumDNS object status | TEXT
SUBCLASS | 1 | 1 | PremiumDNS product class | `2M`, `5M`, `15M`, `30M`, `50M`, `75M`, `100M` or `ENTERPRISE`
USER | 1 | 1 | ID of the user that the PremiumDNS object belongs to | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusPremiumDNS
OBJECTID = 4bf53dce-ba1f-479a-abf5-88481325a5ce
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACCOUNTINGDATE][0] = 2019-05-08 08:20:09
PROPERTY[ACCOUNTINGPERIOD][0] = 0
PROPERTY[CLASS][0] = PREMIUMDNS
PROPERTY[CREATEDDATE][0] = 2017-05-08 08:20:09
PROPERTY[DESCRIPTION][0] = example.zone.
PROPERTY[DNSZONE][0] = example.zone.
PROPERTY[EXPIRATIONDATE][0] = 2019-05-08 08:20:09
PROPERTY[FAILUREDATE][0] = 2019-06-07 08:20:09
PROPERTY[FAILUREPERIOD][0] = 30d
PROPERTY[FINALIZATIONDATE][0] = 2019-05-08 08:20:09
PROPERTY[FINALIZATIONPERIOD][0] = 0
PROPERTY[NEXTACTION][0] = pay
PROPERTY[NEXTACTIONDATE][0] = 2019-05-08 08:20:09
PROPERTY[OBJECTID][0] = 4bf53dce-ba1f-479a-abf5-88481325a5ce
PROPERTY[PAIDUNTILDATE][0] = 2019-05-08 08:20:09
PROPERTY[PEERUSER][0] =
PROPERTY[PREPAIDPERIOD][0] = 0
PROPERTY[RENEWALMODE][0] = AUTORENEW
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[SUBCLASS][0] = STANDARD
PROPERTY[USER][0] = test.user
EOF
```

----
