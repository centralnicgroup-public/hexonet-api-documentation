# UpdateInvoicePDF

## DESCRIPTION
Add or replace the .PDF for a dedicated invoice ID

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateInvoicePDF` | COMMAND
INVOICEID | 1 | The invoice id for which the PDF should be added or replaced  | TEXT
PDF[0..N] | 0 | The content of the new .PDF (base 64 encoded) | TEXT

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
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = UpdateInvoicePDF
INVOICEID = 2007XXXX7
PDF0 = JVBERi0xLjcKMyAwIG9iago8PC9UeXBlIC9QYWdlCi9QYXJlbnQgMSAwIFIKL01lZGlhQm94IFsw
...
PDF6940 = MDAgbiAKdHJhaWxlcgo8PAovU2l6ZSAyMwovUm9vdCAyMiAwIFIKL0luZm8gMjEgMCBSCj4+CnN0
PDF6941 = YXJ0eHJlZgozOTUxMTYKJSVFT0YK
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
