# StatusAccount

## DESCRIPTION
This command returns the account's finance related properties and current values related to finances.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusAccount` | COMMAND

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
AMOUNT | 1 | 1 | The current account balance | DECIMAL
CREDIT | 1 | 1 | The maximum credit volume for this account | DECIMAL
CURRENCY | 1 | 1 | The account's currency | TEXT
DEPOSIT | 1 | 1 | The current reserved deposits | DECIMAL
VAT | 1 | 1 | The VAT for this account in percent (%), e. g. `19.00` | DECIMAL

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusAccount
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[AMOUNT][0] = 217458.12
PROPERTY[CREDIT][0] = 1000000.00
PROPERTY[CURRENCY][0] = EUR
PROPERTY[DEPOSIT][0] = 1658.90
PROPERTY[VAT][0] = 19.00
EOF
```

----
