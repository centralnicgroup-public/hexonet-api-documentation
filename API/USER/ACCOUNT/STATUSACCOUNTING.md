# StatusAccounting

## DESCRIPTION
This command gives you all available information on a certain accounting.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusAccounting` | COMMAND
SUBUSER | 1 | ID of the subuser account | TEXT
ACCOUNTINGID | 1 | ID of the accounting entry | INT

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
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
AMOUNT | 0 | 1 | The amount, e. g. the period for domain registrations | DECIMAL
CURRENCY | 1 | 1 | Currency of the accounting | TEXT
DATE | 0 | 1 | Date of the accounting | DATETIME
DESCRIPTION | 0 | 1 | Description, e. g. a domain name | TEXT
ID | 0 | 1 | ID of the accounting | INT
INVOICEID | 1 | 1 | ID of the invoice to which the accounting may be assigned to | TEXT
PAYMENT | 0 | 1 | The total payment of this accounting without V. A. T. in the account currency | DECIMAL
REFERENCE | 0 | 1 | Field for additional information, e.g. subuser who got charged | TEXT
TYPE | 0 | 1 | Accounting type, e. g. `ADD_DOMAIN` | TEXT
VAT | 0 | 1 | Additional V. A. T. in percent (%), e. g. 19.00 | DECIMAL

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusAccounting
ACCOUNTINGID = 800463
SUBUSER = test.customer
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[AMOUNT][0] = 1.0000
PROPERTY[CURRENCY][0] = EUR
PROPERTY[DATE][0] = 2016-09-20 12:00:00
PROPERTY[DESCRIPTION][0] = example.com
PROPERTY[ID][0] = 800463
PROPERTY[INVOICEID][0] = -
PROPERTY[PAYMENT][0] = -20.00
PROPERTY[REFERENCE][0] =
PROPERTY[TYPE][0] = ADD_DOMAIN
PROPERTY[VAT][0] = 23.00
EOF
```

----
