# GetNextInvoiceID

## DESCRIPTION
This command returns the next invoice ID that the invoice batch will use.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetNextInvoiceID` | COMMAND

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
541 | Invalid attribute value
545 | Object not found

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
INVOICEID | 1 | 1 | The next invoice ID that the invoice batch will use | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetNextInvoiceID
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[INVOICEID][0] = ABC123456
EOF
```

----
