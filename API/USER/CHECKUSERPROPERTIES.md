# CheckUserProperties

## DESCRIPTION
Check the correctness of user properties, as if they were entered in the user registration web form.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckUserProperties` | COMMAND
EMAIL | 0 | An email address | TEXT or NULL
VATID | 0 | VAT registration number | TEXT or NULL
COUNTRY | 0 | 2-letters country code | TEXT or NULL
STATE | 0 | A state, a province, etc. | TEXT or NULL
PASSWORD | 0 | A user password in the first line of the user registration web form | TEXT or NULL
PASSWORD2 | 0 | A user password in the second line of the user registration web form | TEXT or NULL
PHONE | 0 | A phone number | TEXT or NULL
LOGINNAME | 0 | A login name | TEXT or NULL
VIESCHECK | 0 | `0` (default): disable VIES check<br>`1`: enable VIES check | `0`, `1` or NULL
PHONE[0..N] | 0 | Phone numbers | TEXT or NULL
PHONEPREFIX[0..N] | 0 | Phone area codes | TEXT or NULL
EMAIL[0..N] | 0 | Email addresses | TEXT or NULL
ZIP | 0 | Postal ZIP code | TEXT or NULL
RELATION[0..N] | 0 | Price relations | TEXT or NULL
SWIFTBIC | 0 | ISO 9362 Business Identifier Code | TEXT or NULL

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
COUNTRYDATE | 0 | 1 | Country verification date | DATETIME
COUNTRYSTATUSCODE | 0 | 1 | Country verification result code | INT
COUNTRYSTATUSTEXT | 0 | 1 | Country verification result description | TEXT
COUNTRYVALUE | 0 | 1 | Country code | TEXT
COUNTRYVERIFICATION | 0 | 1 | Country verification result | TEXT
EMAIL[0..N]DATE | 0 | N | Email verification date | DATETIME
EMAIL[0..N]STATUSCODE | 0 | N | Email verification result code | INT
EMAIL[0..N]STATUSTEXT | 0 | N | Email verification result description | TEXT
EMAIL[0..N]VALUE | 0 | N | Email address | TEXT
EMAIL[0..N]VERIFICATION | 0 | N | Email verification result | TEXT
EMAILDATE | 0 | 1 | Email verification date | DATETIME
EMAILSTATUSCODE | 0 | 1 | Email verification result code | INT
EMAILSTATUSTEXT | 0 | 1 | Email verification result description | TEXT
EMAILVALUE | 0 | 1 | Email address | TEXT
EMAILVERIFICATION | 0 | 1 | Email verification result | TEXT
LOGINNAMEDATE | 0 | 1 | Login name verification date | DATETIME
LOGINNAMESTATUSCODE | 0 | 1 | Login name verification result code | INT
LOGINNAMESTATUSTEXT | 0 | 1 | Login name verification result description | TEXT
LOGINNAMEVERIFICATION | 0 | 1 | Login name verification result | TEXT
PASSWORDDATE | 0 | 1 | Password verification date | DATETIME
PASSWORDSTATUSCODE | 0 | 1 | Password verification result code | INT
PASSWORDSTATUSTEXT | 0 | 1 | Password verification result description | TEXT
PASSWORDVERIFICATION | 0 | 1 | Password verification result | TEXT
PHONE[0..N]DATE | 0 | N | Phone number verification date | DATETIME
PHONE[0..N]STATUSCODE | 0 | N | Phone number verification result code | INT
PHONE[0..N]STATUSTEXT | 0 | N | Phone number verification result description | TEXT
PHONE[0..N]VALUE | 0 | N | Phone number | TEXT
PHONE[0..N]VERIFICATION | 0 | N | Phone number verification result | TEXT
RELATIONDATE | 0 | 1 | Relation verification date | DATETIME
RELATIONSTATUSCODE | 0 | 1 | Relation verification result code | INT
RELATIONSTATUSTEXT | 0 | 1 | Relation verification result description | TEXT
RELATIONVERIFICATION | 0 | 1 | Relation verification result | TEXT
STATEDATE | 0 | 1 | State verification date | DATETIME
STATESTATUSCODE | 0 | 1 | State verification result code | INT
STATESTATUSTEXT | 0 | 1 | State verification result description | TEXT
STATEVALUE | 0 | 1 | State code | TEXT
STATEVERIFICATION | 0 | 1 | State verification result | TEXT
SWIFTBICDATE | 0 | 1 | SWIFTBIC verification date | DATETIME
SWIFTBICSTATUSCODE | 0 | 1 | SWIFTBIC verification result code | INT
SWIFTBICSTATUSTEXT | 0 | 1 | SWIFTBIC verification result description | TEXT
SWIFTBICVERIFICATION | 0 | 1 | SWIFTBIC verification result | TEXT
VATIDDATE | 0 | 1 | VAT registration number verification date | DATETIME
VATIDSTATUSCODE | 0 | 1 | VAT registration number verification result code | INT
VATIDSTATUSTEXT | 0 | 1 | VAT registration number verification result description | TEXT
VATIDVALUE | 0 | 1 | VAT registration number | TEXT
VATIDVERIFICATION | 0 | 1 | VAT registration number verification result | TEXT
VATIDVIESDATE | 0 | 1 | VIES check date | DATETIME
VATIDVIESSTATUSCODE | 0 | 1 | VIES verification result code | INT
VATIDVIESSTATUSTEXT | 0 | 1 | VIES verification result description | TEXT
VATIDVIESVALUE | 0 | 1 | VAT ID | TEXT
VATIDVIESVERIFICATION | 0 | 1 | VIES verification status | TEXT
ZIPDATE | 0 | 1 | ZIP verification date | DATETIME
ZIPSTATUSCODE | 0 | 1 | ZIP verification result code | INT
ZIPSTATUSTEXT | 0 | 1 | ZIP verification result description | TEXT
ZIPVALUE | 0 | 1 | ZIP postal code | TEXT
ZIPVERIFICATION | 0 | 1 | ZIP verification result | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckUserProperties
COUNTRY = DE
PHONE0 = 445321001
PHONE1 = 15731490123
PHONEPREFIX0 = +380
PHONEPREFIX1 = +49
ZIP = 66424
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[COUNTRYDATE][0] = 2016-09-15 21:43:54
PROPERTY[COUNTRYSTATUSCODE][0] = 200
PROPERTY[COUNTRYSTATUSTEXT][0] = Command completed successfully; Country code is valid
PROPERTY[COUNTRYVALUE][0] = DE
PROPERTY[COUNTRYVERIFICATION][0] = SUCCESS
PROPERTY[PHONE0DATE][0] = 2016-09-15 21:43:54
PROPERTY[PHONE0STATUSCODE][0] = 200
PROPERTY[PHONE0STATUSTEXT][0] = Number is valid
PROPERTY[PHONE0VALUE][0] = 445321001
PROPERTY[PHONE0VERIFICATION][0] = SUCCESS
PROPERTY[PHONE1DATE][0] = 2016-09-15 21:43:54
PROPERTY[PHONE1STATUSCODE][0] = 200
PROPERTY[PHONE1STATUSTEXT][0] = Number is valid
PROPERTY[PHONE1VALUE][0] = 15731490123
PROPERTY[PHONE1VERIFICATION][0] = SUCCESS
PROPERTY[ZIPDATE][0] = 2016-09-15 21:43:54
PROPERTY[ZIPSTATUSCODE][0] = 200
PROPERTY[ZIPSTATUSTEXT][0] = Syntax check ok
PROPERTY[ZIPVALUE][0] = 66424
PROPERTY[ZIPVERIFICATION][0] = SUCCESS
EOF
```

----
