# QueryObjectRenewalList

## DESCRIPTION
Query a list of objects that have to be renewed. The time interval can be specified with the parameters described in the table below.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryObjectRenewalList` | COMMAND
WIDE | 0 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`OBJECTIDDESC`, `OBJECTCLASS`, `OBJECTCLASSDESC`, `EXPIRATIONDATE`, `EXPIRATIONDATEDESC`, `PAIDUNTILDATE`, `PAIDUNTILDATEDESC`, `ACCOUNTINGDATE`, `ACCOUNTINGDATEDESC`, `FINALIZATIONDATE`, `FINALIZATIONDATEDESC`, `FAILUREDATE`, `FAILUREDATEDESC`, `NEXTACTIONDATE`, `NEXTACTIONDATEDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be: `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
SUBUSER | 0 | User ID of the subuser | TEXT
OBJECTCLASS | 0 | CLASS of the object, e.g. `DOMAIN` | PATTERN
OBJECTID | 0 | ID of an object, e.g. `example.com` | PATTERN
REPOSITORY | 0 | Filter output by a specific domain repository | PATTERN
OBJECTSUBCLASS | 0 | Filter output by a specific subclass | PATTERN
RENEWALMODE | 0 | Renewal mode, e.g. `renew` | PATTERN
MINEXPIRATIONDATE | 0 | First expiration date to be returned | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Last expiration date to be returned | NULL or TEXT
MINPAIDUNTILDATE | 0 | First paiduntildate to be returned | NULL or TEXT
MAXPAIDUNTILDATE | 0 | Last paiduntildate to be returned | NULL or TEXT
MINACCOUNTINGDATE | 0 | First accounting date to be returned | NULL or TEXT
MAXACCOUNTINGDATE | 0 | Last accounting date to be returned | NULL or TEXT
MINFINALIZATIONDATE | 0 | First finalization date to be returned | NULL or TEXT
MAXFINALIZATIONDATE | 0 | Last finalization date to be returned | NULL or TEXT
MINFAILUREDATE | 0 | First failure date to be returned | NULL or TEXT
MAXFAILUREDATE | 0 | Last failure date to be returned | NULL or TEXT
MINREGISTRATIONEXPIRATIONDATE | 0 | First registration expiration date | NULL or TEXT
MAXREGISTRATIONEXPIRATIONDATE | 0 | Last registration expiration date | NULL or TEXT


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
507 | User session expired
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | Number of entries showing | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
ACCOUNTINGDATE[0..N] | 0 | N | Accounting date | DATETIME
DESCRIPTION[0..N] | 0 | N | Object description | TEXT
EXPIRATIONDATE[0..N] | 0 | N | Expiration date | DATETIME
FAILUREDATE[0..N] | 0 | N | Failure date | DATETIME
FINALIZATIONDATE[0..N] | 0 | N | Finalization date | DATETIME
NEXTACTION[0..N] | 0 | N | Next action for the object, delete, expire, expireunpaid, finalize, pay | TEXT
NEXTACTIONDATE[0..N] | 0 | N | Date of the next action | DATETIME
OBJECTCLASS[0..N] | 0 | N | The object class | PATTERN
OBJECTID[0..N] | 0 | N | The object ID | PATTERN
PAIDUNTILDATE[0..N] | 0 | N | Paid until date | DATETIME
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PERIOD[0..N] | 0 | N | Only returned if wide is set to `1`: period for the upcoming renewal | TEXT   
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
PRICE[0..N] | 0 | N | Only returned if wide is set to `1`: price for the upcoming renewal| TEXT
REGISTRATIONEXPIRATIONDATE[0..N] | 0 | N | Registration expiration date | DATETIME
RENEWALMODE[0..N] | 0 | N | The object's renewal mode | TEXT
RENEWALPERIOD[0..N] | 0 | N | The object's renewal period | TEXT
SUBCLASS[0..N] | 0 | N | The respective subclass | TEXT
USER[0..N] | 0 | N | The user ID | TEXT
VAT[0..N] | 0 | N | Only returned if wide is set to `1`: VAT for the upcoming renewal | TEXT
VATPRICE[0..N] | 0 | N | Only returned if wide is set to `1`: VAT price for the upcoming renewal| TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryObjectRenewalList
FIRST = 2
LIMIT = 2
USERDEPTH = SELF
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 2
PROPERTY[LAST][0] = 3
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 1760
PROPERTY[LIMIT][0] = 2
PROPERTY[ACCOUNTINGDATE][0] = 2013-08-24 07:03:56
PROPERTY[ACCOUNTINGDATE][1] = 2013-08-24 07:18:11
PROPERTY[DESCRIPTION][0] = sdfsfsdfsfdsd.de
PROPERTY[DESCRIPTION][1] = pppoaoda.de
PROPERTY[EXPIRATIONDATE][0] = 2013-08-31 07:03:56
PROPERTY[EXPIRATIONDATE][1] = 2013-08-31 07:18:11
PROPERTY[FAILUREDATE][0] = 2013-08-30 07:03:56
PROPERTY[FAILUREDATE][1] = 2013-08-30 07:18:11
PROPERTY[FINALIZATIONDATE][0] = 2013-08-30 07:03:56
PROPERTY[FINALIZATIONDATE][1] = 2013-08-30 07:18:11
PROPERTY[NEXTACTION][0] = expire
PROPERTY[NEXTACTION][1] = expire
PROPERTY[NEXTACTIONDATE][0] = 2013-08-30 07:03:56
PROPERTY[NEXTACTIONDATE][1] = 2013-08-30 07:18:11
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTCLASS][1] = DOMAIN
PROPERTY[OBJECTID][0] = sdfsfsdfsfdsd.de
PROPERTY[OBJECTID][1] = pppoaoda.de
PROPERTY[PAIDUNTILDATE][0] = 2013-08-31 07:03:56
PROPERTY[PAIDUNTILDATE][1] = 2013-08-31 07:18:11
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2015-12-02 19:03:56
PROPERTY[REGISTRATIONEXPIRATIONDATE][1] = 2015-12-02 19:18:11
PROPERTY[RENEWALMODE][0] = expire
PROPERTY[RENEWALMODE][1] = expire
PROPERTY[RENEWALPERIOD][0] =
PROPERTY[RENEWALPERIOD][1] =
PROPERTY[SUBCLASS][0] = DE
PROPERTY[SUBCLASS][1] = DE
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
## NOTES
* USERDEPTH defines the depth of the returned list. `SELF` returns a list with only objects of the user itself. `SUBUSER` returns a list with objects of all direct subusers. `ALL` returns a list with objects of all subusers and all subusers below them.
* FIRST and LIMIT should be used to implement paging.
