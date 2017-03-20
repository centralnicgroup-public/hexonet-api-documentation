# QueryInvoiceList

## DESCRIPTION
This command returns a list of the invoices, issued to the user, executing the command, or its subusers.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryInvoiceList` | COMMAND
USERDEPTH | 0 | Show only invoices with the following recipient(s):<br>`SELF` (default value): the user, executing the command;<br>`SUBUSER`: subuser(s) of the user, executing the command | `SELF` or `SUBUSER`
SUBUSER | 0 | Execute the command as if it were executed by a subuser with `SUBUSER` account ID | TEXT
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Maximal number of entries to be returned | INT
DATA[0..N] | 0 | Show only invoices with given invoice details | PATTERN
DATATYPE[0..N] | 0 | Return invoice details data of given types  | TEXT
ORDERBY | 0 | Order the response list by:<br>`DATE`: invoice issue date, ascending;<br>`DATEDESC`: invoice issue date, descending;<br>`INVOICEID`: invoice ID, ascending;<br>`INVOICEIDDESC`: invoice ID, descending | `DATE`, `DATEDESC`, `INVOICEID`, `INVOICEIDDESC` or NULL
MININVOICEID | 0 | The minimal invoice ID in the response list | TEXT
MAXINVOICEID | 0 | The maximal invoice ID in the response list | TEXT
MINDATE | 0 | The minimal invoice issue date | DATE or NULL
MAXDATE | 0 | The maximal invoice issue date | DATE or NULL
STATUS | 0 | Show only invoices with the given status:<br>`NEW`<br>`ACTIVE`<br>`CANCELED` | TEXT or NULL

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (maximal number of entries returned) | INT
CREATEDDATE[0..N] | 0 | N | Invoice creation date | DATETIME
DATAVALUE0..N[0..N] | 0 | N | Invoice detail value | TEXT
INVOICEID[0..N] | 0 | N | Invoice ID | TEXT
STATUS[0..N] | 0 | N | Invoice status | TEXT
USER[0..N] | 0 | N | Invoice recipient user ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryInvoiceList
DATA0 = recipient_email:test*
DATATYPE0 = recipient_phone
DATATYPE1 = recipient_email
LIMIT = 2
ORDERBY = DATE
USERDEPTH = SUBUSER
EOF
```
### Response

```

[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 2
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2016-11-10 10:41:34
PROPERTY[CREATEDDATE][1] = 2016-11-11 05:25:42
PROPERTY[DATAVALUE0][0] = +49.234123456
PROPERTY[DATAVALUE0][1] = +49.234324723
PROPERTY[DATAVALUE1][0] = test.guest@example.com
PROPERTY[DATAVALUE1][1] = test.guest@example.com
PROPERTY[INVOICEID][0] = ABC123456
PROPERTY[INVOICEID][1] = ABC123457
PROPERTY[STATUS][0] = NEW
PROPERTY[STATUS][1] = NEW
PROPERTY[USER][0] = test.guest
PROPERTY[USER][1] = test.guest
EOF
```

----
