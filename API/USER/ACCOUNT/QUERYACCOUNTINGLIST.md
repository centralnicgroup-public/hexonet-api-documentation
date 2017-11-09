# QueryAccountingList

## DESCRIPTION
Query the accounting list of the user account or a subuser.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryAccountingList` | COMMAND
SUBUSER | 0 | ID of the subuser account | TEXT
MINDATE | 0 | First accounting date to be returned | TEXT
MAXDATE | 0 | Last accounting date to be returned | TEXT
FIRST | 0 | The index of the first entry to be returned | INT
LIMIT | 0 | Maximum number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | Sort response by certain criteria e.g. `ACCOUNTINGID`. <br> Queries with `ACCOUNTINGDATEONLY` as the ORDERBY parameter have a higher performance compared to queries with `ACCOUNTINGDATE`. <br> `ACCOUNTINGDATE` however has the effect that the accountings are always listed in the exact same execution order. When a query with `ACCOUNTINGDATE` is executed it may be the case that accountings with the same timestamp are mixed up | `ACCOUNTINGID`, `ACCOUNTINGTYPE`, `ACCOUNTINGDATE`, `ACCOUNTINGDATEDESC`, `ACCOUNTINGDATEONLY`, `ACCOUNTINGDATEONLYDESC`, `INVOICEID`, `REFERENCE` or NULL
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF` or `SUBUSER`
INVOICEID | 0 | Query for a specific invoice ID | TEXT
TYPE | 0 | Type of accounting | TEXT
WIDE | 0 | If set to `1`: verbose output (more parameters) | `0` or `1`
DESCRIPTION | 0 | Description that was entered with the accounting (e.g. domain name) | TEXT
REFERENCE | 0 | Payment reference, e.g. ID of a subuser | TEXT or NULL
TASK | 0 | The task for which the command gets executed. e.g. for the creation of a invoice. When stated must be either `INVOICECREATE` or `PAYMENTLIST` | TEXT or NULL
NOSUM | 0 | Set to `1` to suppress the display of sum properties. This will improves the performance significantly | `0` or `1`
TYPEREGEX | 0 | Only return records matching the regexp | TEXT or NULL
TYPEREGEXNOT | 0 | Only return records not matching the regexp | TEXT or NULL

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
ACCOUNTINGAMOUNT[0..N] | 0 | N | The amount, e. g. the period for domain registrations | DECIMAL
ACCOUNTINGCURRENCY | 0 | N | The currency of the accounting | TEXT
ACCOUNTINGDATE[0..N] | 0 | N | Date of the accounting list entry | DATETIME
ACCOUNTINGDESCRIPTION[0..N] | 0 | N | Description, e. g. a domain name | TEXT
ACCOUNTINGID[0..N] | 0 | N | ID of the accounting list entry (only shown if the user is different from the subuser) | INT
ACCOUNTINGINVOICEID[0..N] | 0 | N | The respective invoice ID | TEXT
ACCOUNTINGPRICE[0..N] | 0 | N | The total price of this accounting entry without V. A. T. in the account currency | DECIMAL
ACCOUNTINGREFERENCE[0..N] | 0 | N | Reference, e. g. ID of the subuser causing that accounting list entry | TEXT
ACCOUNTINGTYPE[0..N] | 0 | N | Accounting type, e. g. ADD_DOMAIN | TEXT
ACCOUNTINGVAT[0..N] | 0 | N | Additional V. A. T. in percent (%), e. g. 16.00 | DECIMAL
ACCOUNTINGVATPRICE[0..N] | 0 | N | Additional V. A. T. in the account currency | DECIMAL
OPENINGBALANCE | 0 | 1 | Opening Balance including V. A. T. | DECIMAL
OPENINGBALANCEPRICE | 0 | 1 | Opening balance without V. A. T. | DECIMAL
OPENINGBALANCEVATPRICE | 0 | 1 | The V. A. T. included in the opening balance | DECIMAL
SUM | 0 | 1 | Sum of the opening balance and the positions | DECIMAL
SUMPRICE | 0 | 1 | Sum of the opening balance without V. A. T. and the positions without V. A. T. | DECIMAL
SUMVATPRICE | 0 | 1 | The V. A. T. Included in the sum | DECIMAL


----
## Example

### Command

```
[COMMAND]
COMMAND = QueryAccountingList
MAXDATE = 2016-09-21 23:59:59
MINDATE = 2016-09-20 00:00:00
SUBUSER = test.customer
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
PROPERTY[LIMIT][0] = 1000
PROPERTY[ACCOUNTINGAMOUNT][0] = 1
PROPERTY[ACCOUNTINGAMOUNT][1] = 1
PROPERTY[ACCOUNTINGCURRENCY][0] = eur
PROPERTY[ACCOUNTINGCURRENCY][1] = eur
PROPERTY[ACCOUNTINGDATE][0] = 2016-09-20 12:00:00
PROPERTY[ACCOUNTINGDATE][1] = 2016-09-21 14:15:52
PROPERTY[ACCOUNTINGDESCRIPTION][0] = example.com
PROPERTY[ACCOUNTINGDESCRIPTION][1] = PayPal Payment
PROPERTY[ACCOUNTINGID][0] = 800463
PROPERTY[ACCOUNTINGID][1] = 800477
PROPERTY[ACCOUNTINGINVOICEID][0] = -
PROPERTY[ACCOUNTINGINVOICEID][1] = +
PROPERTY[ACCOUNTINGPRICE][0] = -20.00
PROPERTY[ACCOUNTINGPRICE][1] = 150.00
PROPERTY[ACCOUNTINGREFERENCE][0] =
PROPERTY[ACCOUNTINGREFERENCE][1] =
PROPERTY[ACCOUNTINGTYPE][0] = ADD_DOMAIN
PROPERTY[ACCOUNTINGTYPE][1] = PAYMENT
PROPERTY[ACCOUNTINGVAT][0] = 23.00
PROPERTY[ACCOUNTINGVAT][1] = 0.00
PROPERTY[ACCOUNTINGVATPRICE][0] = -4.60
PROPERTY[ACCOUNTINGVATPRICE][1] = 0.00
PROPERTY[OPENINGBALANCE][0] = 0.00
PROPERTY[OPENINGBALANCEPRICE][0] = 0.00
PROPERTY[OPENINGBALANCEVATPRICE][0] = 0.00
PROPERTY[SUM][0] = 125.40
PROPERTY[SUMPRICE][0] = 130.00
PROPERTY[SUMVATPRICE][0] = -4.60
EOF
```

----
## NOTES

* If mindate is without the time part, then `00:00:00` will be appended, e. g. `2016-09-01` becomes `2016-09-01 00:00:00`.
* If maxdate is without the time part, then `23:59:59` will be appended, e. g. `2016-09-01` becomes `2016-09-01 23:59:59`.
