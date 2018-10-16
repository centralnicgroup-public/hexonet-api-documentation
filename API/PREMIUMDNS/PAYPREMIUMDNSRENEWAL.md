# PayPremiumDNSRenewal

## DESCRIPTION
Pay for the next renewal of a PremiumDNS object.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `PayPremiumDNSRenewal` | COMMAND
OBJECTID | 1 | PremiumDNS object ID | TEXT
ORDER | 0 | PremiumDNS payment order action:<br>`CREATE` - create a PremiumDNS payment order<br>`REPLACE` - replace a PremiumDNS payment order<br>`UPDATE` - update a PremiumDNS payment order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | PremiumDNS payment order ID; only relevant if ORDER is `REPLACE` or `UPDATE` | INT
PERIOD | 0 | Validity period; the default is: `1Y` | PERIOD

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
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EXPIRATIONDATE | 1 | 1 | Expiration date of the PremiumDNS object | DATETIME
PAIDUNTILDATE | 1 | 1 | Paid until date of the PremiumDNS object | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = PayPremiumDNSRenewal
OBJECTID = 4bf53dce-ba1f-479a-abf5-88481325a5ce
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EXPIRATIONDATE][0] = 2019-05-08 08:20:09
PROPERTY[PAIDUNTILDATE][0] = 2020-05-07 08:20:09
EOF
```

----
