# PayWebsiteRenewal

## DESCRIPTION
Pay for the next renewal of a WEBSITE object.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `PayWebsiteRenewal` | COMMAND
ID | 1 | ID of the website | INT
ORDER | 0 | WEBSITE payment order action:<br>`CREATE` - create a WEBSITE payment order<br>`REPLACE` - replace a WEBSITE payment order<br>`UPDATE` - update a WEBSITE payment order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | WEBSITE payment order ID; only relevant if ORDER is `REPLACE` or `UPDATE` | INT
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
505 | Invalid attribute value syntax
530 | Authentication failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EXPIRATIONDATE | 1 | 1 | The current expiration date of the website | DATETIME
PAIDUNTILDATE | 1 | 1 | The expiration date of the website | DATETIME

## Example

### Command

```
[COMMAND]
COMMAND = PayWebsiteRenewal
OBJECTID = 264287657782855697
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EXPIRATIONDATE][0] = 2021-03-18 14:23:59
PROPERTY[PAIDUNTILDATE][0] = 2020-03-18 14:23:59
EOF
```

----
