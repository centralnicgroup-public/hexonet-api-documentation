# UpdateInvoice

## DESCRIPTION
This command allows to update an invoice.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateInvoice` | COMMAND
INVOICEID | 1 | Invoice ID | TEXT
CREATEDDATE | 0 | Invoice issue date | TEXT
FLUSHDATA | 0 | If set to `1`, then all data, related to the affected invoice (which were provided previously through the `DATA[0..N]` arguments of the commands `CreateInvoice` and `UpdateInvoice`), will be deleted before the update | `0` or `1`
DATA[0..N] | 0 | Invoice data in the format `key:value` | TEXT
STATUS | 0 | New invoice status | `NEW`, `ACTIVE` or `CANCELED`
FLUSHPDF | 0 | If set to 1, removes the PDF version of the invoice, if existing | `0` or `1`
REFRESHRECIPIENT | 0 | Resets the recipient information stored with the invoice (using the user data of the recipient) | `0` or `1`
REFRESHSENDER | 0 | Resets the sender information stored with the invoice (using the user data of the invoicing party) | `0` or `1`
REFRESHTEMPLATE | 0 | Resets the template information stored with the invoice (using the template data of the invoicing party) | `0` or `1`
VAT | 0 | If given, updates the TAX rate of all accounting items that are assigned to the respective invoice | `/^[0-9]+(\.[0-9]+)?$/`

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

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = UpdateInvoice
DATA0 = recipient_phone:+49.234123456
DATA1 = recipient_fax:+49.234654321
INVOICEID = ABC123456
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
