# AddAccounting

## DESCRIPTION
Add an accounting into the accounting list of a subuser's account.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AddAccounting` | COMMAND
SUBUSER | 1 | ID of the subuser account | TEXT
DESCRIPTION | 1 | Description of this accounting entry | TEXT
TYPE | 1 | Type of this accounting entry, e.g. `PAYMENT` or `ADD_DOMAIN`.<br> Only allowed characters are capital letters, digits, "_" and "/"| `/^[A-Z0-9\_\/]+$/`
AMOUNT | 0 | The amount, e. g. the period for domain registrations, default = `1`. <br> Only allowed values are non-negative integers and decimals | `/^[0-9]+(\.[0-9]+)?$/`
PAYMENT | 1 | Payment made to the account, debited if < `0`. <br> Only allowed values are negative and non-negative decimals with exactly two decimal places, e.g. `-12.99`  | `/^\-?[0-9]+\.[0-9][0-9]$/`
VAT | 0 | Additional VAT %, default = vat of the subuser account. <br> Only allowed values are non-negative integers and decimals | `/^[0-9]+(\.[0-9]+)?$/`
REFERENCE | 0 | Payment reference, e.g. ID of a subuser | TEXT or NULL
DATE | 0 | Date of the payment.<br> Only dates with or without a timestamp in the format of YYYY-MM-DD and respectively YYYY-MM-DD HH:MM:SS are allowed | `/^[0-9][0-9][0-9][0-9]\-[0-9][0-9]\-[0-9][0-9]([ ][0-9][0-9]\:[0-9][0-9]\:[0-9][0-9])?$/`
INVOICEID | 0 | Link this accounting to a specific invoice ID. If not provided this parameter will be automatically set to `+` in case TYPE was set to PAYMENT and to `-` if TYPE was set to a value other than PAYMENT | TEXT or NULL
CURRENCY | 0 | Currency of the payment(will be automatically calculated to the user's account currency) | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Syntax error in Parameter
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACCOUNTINGID | 1 | 1 | ID of the Accounting created | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = AddAccounting
DESCRIPTION = PayPal Payment
PAYMENT = 150.00
SUBUSER = test.customer
TYPE = PAYMENT
VAT = 0.00
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACCOUNTINGID][0] = 800464
EOF
```

----
## NOTES

* For payments, the type should always be PAYMENT and the V.A.T. should be 0.00.
