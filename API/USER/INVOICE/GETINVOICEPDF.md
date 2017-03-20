# GetInvoicePDF

## DESCRIPTION
Query a previously created .PDF for a dedicated invoice id

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetInvoicePDF` | COMMAND
INVOICEID | 1 | Invoice ID for which a .PDF was previously created | TEXT
USERDEPTH | 0 | USERDEPTH defines the depth of the returned list. `SELF` returns a list with only objects of the user itself. `SUBUSER` returns a list with objects of all direct subusers. | `SELF` or `SUBUSER`

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
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDBY | 1 | 1 | User who created the invoice | TEXT
CREATEDDATE | 1 | 1 | Creation date of the invoice | DATETIME
INVOICEGUID | 1 | 1 | GUID of the invoice | TEXT
INVOICEID | 1 | 1 | ID of the invoice | TEXT
PDF[0..N] | 0 | N | Raw .PDF data | TEXT
PDFUPDATEDDATE | 1 | 1 | Updated date of the invoice | DATETIME
STATUS | 1 | 1 | Status of the invoice | TEXT
USER | 1 | 1 | User that executed the command | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = GetInvoicePDF
INVOICEID = 2007XXXX7
USERDEPTH = subuser
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDBY][0] = demo.hexonet.net
PROPERTY[CREATEDDATE][0] = 2009-12-15 15:46:17
PROPERTY[INVOICEGUID][0] = 4B27B0930F98542C
PROPERTY[INVOICEID][0] = 2007XXXX7
PROPERTY[PDF][0] = JVBERi0xLjcKMyAwIG9iago8PC9UeXBlIC9QYWdlCi9QYXJlbnQgMSAwIFIKL01lZGlhQm94IFsw
...
PROPERTY[PDF][6940] = MDAgbiAKdHJhaWxlcgo8PAovU2l6ZSAyMwovUm9vdCAyMiAwIFIKL0luZm8gMjEgMCBSCj4+CnN0
PROPERTY[PDF][6941] = YXJ0eHJlZgozOTUxMTYKJSVFT0YK
PROPERTY[PDFUPDATEDDATE][0] = 2016-12-01 23:12:11
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[USER][0] = test.user
EOF
```

----
