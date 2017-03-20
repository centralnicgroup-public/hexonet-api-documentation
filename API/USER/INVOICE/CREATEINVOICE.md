# CreateInvoice

## DESCRIPTION
This command allows to create an invoice to a subuser. The created invoice does not contain any accounting items, they should be added to the invoice with the command `AssignInvoiceItems`. The created invoice gets always the status `NEW` and is not visible to the recipient.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateInvoice` | COMMAND
INVOICEID | 1 | Invoice ID should have a length between 2 and 32 characters and may contain only letters of the English alphabet and digits | TEXT
SUBUSER | 1 | Subuser account ID | TEXT
CREATEDDATE | 0 | Invoice issue date | TEXT
DATA[0..N] | 0 | Invoice data in the format `key:value`; it can be invoice template details like issuer bank account number, recipient email address, etc. | TEXT
ACCOUNTING-INVOICEID | 0 | Only consider accountings that are already assigned to this ACCOUNTING-INVOICEID and assign them to the given INVOICEID | TEXT
ACCOUNTING-MAXDATE | 0 | Only consider accountings which have been created on or before this date and assign them to the given INVOICEID | TEXT
ACCOUNTING-MINDATE | 0 | Only consider accountings which have been created on or after this date and assign them to the given INVOICEID | TEXT


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
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDDATE | 0 | 1 | Invoice issue date | DATETIME
STATUS | 0 | 1 | Invoice status | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CreateInvoice
DATA0 = recipient_phone:+49.234324723
DATA1 = recipient_fax:+49.234324836
DATA2 = recipient_email:test.guest@example.com
INVOICEID = ABC123456
SUBUSER = test.guest
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2016-11-10 10:41:34
PROPERTY[STATUS][0] = NEW
EOF
```

----
