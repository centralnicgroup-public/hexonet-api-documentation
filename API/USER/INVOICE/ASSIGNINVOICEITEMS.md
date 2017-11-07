# AssignInvoiceItems

## DESCRIPTION
This command allows to bind accounting operations, made by a subuser, to an existing invoice.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AssignInvoiceItems` | COMMAND
INVOICEID | 1 | Invoice ID | TEXT
SUBUSER | 1 | Subuser account ID | TEXT
ACCOUNTINGID[0..N] | 1 | Accounting operation IDs | INT

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
540 | Attribute value is not unique
541 | Invalid attribute value

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = AssignInvoiceItems
ACCOUNTINGID0 = 978234
INVOICEID = ABC1234567
SUBUSER = subuser.test
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
