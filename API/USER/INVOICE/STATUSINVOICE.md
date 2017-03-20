# StatusInvoice

## DESCRIPTION
This command shows the status of an issued invoice.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusInvoice` | COMMAND
INVOICEID | 1 | Invoice ID | TEXT
USERDEPTH | 0 | `SELF`: get information about an invoice, issued to the user, executing the command; default value<br>`SUBUSER`: get information about an invoice, issued by the user, executing the command  | `SELF` or `SUBUSER`

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
CREATEDBY | 1 | 1 | User account ID of the invoice issuer | TEXT
CREATEDDATE | 1 | 1 | Invoice issue date | DATETIME
DATATYPE[0..N] | 0 | N | Invoice data type | TEXT
DATAVALUE[0..N] | 0 | N | Invoice data value | TEXT
INVOICEGUID | 1 | 1 | Invoice GUID | TEXT
INVOICEID | 1 | 1 | Invoice ID | TEXT
STATUS | 1 | 1 | Invoice status:<br>`NEW` - default invoice status after its creation; a new invoice is not visible to the recipient and may be changed by the issuer <br>`ACTIVE` - an actvie invoice is visible to the recipient and can not be changed<br>`CANCELED` - the invoice is canceled | TEXT
USER | 0 | 1 | Subuser account ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusInvoice
INVOICEID = ABC123456
USERDEPTH = SUBUSER
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDBY][0] = test.user
PROPERTY[CREATEDDATE][0] = 2016-11-10 10:41:34
PROPERTY[DATATYPE][0] = recipient_email
PROPERTY[DATATYPE][1] = recipient_fax
PROPERTY[DATATYPE][2] = recipient_phone
PROPERTY[DATAVALUE][0] = test.guest@example.com
PROPERTY[DATAVALUE][1] = +49.234324836
PROPERTY[DATAVALUE][2] = +49.234324723
PROPERTY[INVOICEGUID][0] = 58244EDEEF676933
PROPERTY[INVOICEID][0] = ABC123456
PROPERTY[STATUS][0] = NEW
PROPERTY[USER][0] = test.guest
EOF
```

----
