# ModifyAccounting

## DESCRIPTION
Modify an existing accounting entry.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyAccounting` | COMMAND
SUBUSER | 1 | ID of the subuser account | TEXT
ACCOUNTINGID | 1 | Accounting ID (as got from command QueryAccountingList) | INT
DESCRIPTION | 0 | Description of this accounting entry | TEXT
TYPE | 0 | Type of this accounting entry, e.g. `PAYMENT`.<br> Only allowed characters are capital letters, digits, "_" and "/" | `/^[A-Z0-9\_\/]+$/`
AMOUNT | 0 |  The amount, e. g. the period for domain registrations, default = `1`. <br> Only allowed values are non-negative integers and decimals | `/^[0-9]+(\.[0-9]+)?$/`
PAYMENT | 0 | Payment made to the account, debited if < `0`. <br> Only allowed values are negative and non-negative decimals with exactly two decimal places, e.g. `-12.99` | `/^\-?[0-9]+\.[0-9][0-9]$/`
VAT | 0 | Additional VAT %, default = vat of the subuser account. <br> Only allowed values are non-negative integers and decimals | `/^[0-9]+(\.[0-9]+)?$/`
REFERENCE | 0 | Payment reference, e. g. ID of a subuser | TEXT or NULL
DATE | 0 | Date of the payment.<br> Only dates with or without a timestamp in the format of YYYY-MM-DD and respectively YYYY-MM-DD HH:MM:SS are allowed | `/^[0-9][0-9][0-9][0-9]\-[0-9][0-9]\-[0-9][0-9]([ ][0-9][0-9]\:[0-9][0-9]\:[0-9][0-9])?$/`
INVOICEID | 0 | Invoice ID | TEXT or NULL

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
549 | Command Failed


No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyAccounting
ACCOUNTINGID = 800463
DATE = 2016-09-20 12:00:00
SUBUSER = test.customer
VAT = 23.00
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
## NOTES

* For payments, the type should always be PAYMENT and the V.A.T. should be 0.00.
