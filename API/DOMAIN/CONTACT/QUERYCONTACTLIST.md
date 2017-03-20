# QueryContactList

## DESCRIPTION
Query a list of contacts.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryContactList` | COMMAND
WIDE | 0 | Return some additional object properties | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Maximum number of entries to be returned | INT
ORDERBY | 0 | Sort by `CONTACT`, `CONTACTDESC`, `USER`, `USERDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
CONTACT | 0 | Pattern for the contact ID, e. g. `P-A*` | PATTERN
TITLE | 0 | Pattern for the contact title, e. g. `P-A*` | TEXT
FIRSTNAME | 0 | Pattern for the contact first name | TEXT
MIDDLENAME | 0 | Pattern for the contact middle name | TEXT
LASTNAME | 0 | Pattern for the contact last name | TEXT
ORGANIZATION | 0 | Pattern for the contact organization | TEXT
STREET | 0 | Pattern for the contact street | TEXT
CITY | 0 | Pattern for the contact city | TEXT
STATE | 0 | Pattern for the contact state | TEXT
ZIP | 0 | Pattern for the contact zip | TEXT
COUNTRY | 0 | Pattern for the contact country | TEXT
PHONE | 0 | Pattern for the contact phone number | TEXT
FAX | 0 | Pattern for the contact fax number | TEXT
EMAIL | 0 | Pattern for the contact email address | TEXT
STATUS | 0 | Search for: e.g. status `DELETED` | TEXT
MINCREATEDDATE | 0 | Search for: Minimal creating date | NULL or TEXT
MAXCREATEDDATE | 0 | Search for: Maximal creating date | NULL or TEXT
MINUPDATEDDATE | 0 | Search for: Minimal update date | NULL or TEXT
MAXUPDATEDDATE | 0 | Search for: Maximal update date | NULL or TEXT

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
CONTACT[0..N] | 0 | N | The contact ID | TEXT
CONTACTCITY[0..N] | 0 | N | The contact city (only returned if wide=1) | TEXT
CONTACTCOUNTRY[0..N] | 0 | N | The contact country (only returned if wide=1) | TEXT
CONTACTCREATEDDATE[0..N] | 0 | N | The contact create date (only returned if wide=1) | DATETIME
CONTACTEMAIL[0..N] | 0 | N | The contact email address (only returned if wide=1) | TEXT
CONTACTFAX[0..N] | 0 | N | The contact fax number (only returned if wide=1) | TEXT
CONTACTFIRSTNAME[0..N] | 0 | N | The contact first name (only returned if wide=1) | TEXT
CONTACTLASTNAME[0..N] | 0 | N | The contact last name (only returned if wide=1) | TEXT
CONTACTMIDDLENAME[0..N] | 0 | N | The contact middle name (only returned if wide=1) | TEXT
CONTACTORGANIZATION[0..N] | 0 | N | The contact organization (only returned if wide=1) | TEXT
CONTACTPHONE[0..N] | 0 | N | The contact phone number (only returned if wide=1) | TEXT
CONTACTSTATE[0..N] | 0 | N | The contact state (only returned if wide=1) | TEXT
CONTACTSTATUS[0..N] | 0 | N | The status of the contact object | TEXT
CONTACTSTREET[0..N] | 0 | N | The contact street (only returned if wide=1) | TEXT
CONTACTTITLE[0..N] | 0 | N | The contact title (only returned if wide=1) | TEXT
CONTACTUPDATEDDATE[0..N] | 0 | N | The contact update date (only returned if wide=1) | DATETIME
CONTACTZIP[0..N] | 0 | N | The contact zip (only returned if wide=1) | TEXT
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
USER[0..N] | 0 | N | The user ID | TEXT



----
## Example

### Command

```
[COMMAND]
COMMAND = QueryContactList
LIMIT = 2
MINCREATEDDATE = 2016-10-04 12:00:00
WIDE = 1
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
PROPERTY[CONTACT][0] = P-TCN1378880
PROPERTY[CONTACT][1] = P-TCN1378881
PROPERTY[CONTACTCITY][0] = Samplecity
PROPERTY[CONTACTCITY][1] = Samplecity
PROPERTY[CONTACTCOUNTRY][0] = DE
PROPERTY[CONTACTCOUNTRY][1] = DE
PROPERTY[CONTACTCREATEDDATE][0] = 2016-10-04 14:05:47
PROPERTY[CONTACTCREATEDDATE][1] = 2016-10-04 14:06:04
PROPERTY[CONTACTEMAIL][0] = test@example.com
PROPERTY[CONTACTEMAIL][1] = test@example.com
PROPERTY[CONTACTFAX][0] =
PROPERTY[CONTACTFAX][1] =
PROPERTY[CONTACTFIRSTNAME][0] = Test
PROPERTY[CONTACTFIRSTNAME][1] = Test2
PROPERTY[CONTACTLASTNAME][0] = Contact
PROPERTY[CONTACTLASTNAME][1] = Contact
PROPERTY[CONTACTMIDDLENAME][0] =
PROPERTY[CONTACTMIDDLENAME][1] =
PROPERTY[CONTACTORGANIZATION][0] =
PROPERTY[CONTACTORGANIZATION][1] =
PROPERTY[CONTACTPHONE][0] = +49.1234567890
PROPERTY[CONTACTPHONE][1] = +49.1234567890
PROPERTY[CONTACTSTATE][0] =
PROPERTY[CONTACTSTATE][1] =
PROPERTY[CONTACTSTATUS][0] = ACTIVE
PROPERTY[CONTACTSTATUS][1] = ACTIVE
PROPERTY[CONTACTSTREET][0] = Samplestreet 42
PROPERTY[CONTACTSTREET][1] = Samplestreet 42
PROPERTY[CONTACTTITLE][0] =
PROPERTY[CONTACTTITLE][1] =
PROPERTY[CONTACTUPDATEDDATE][0] = 2016-10-04 14:05:47
PROPERTY[CONTACTUPDATEDDATE][1] = 2016-10-04 14:06:04
PROPERTY[CONTACTZIP][0] = 123456
PROPERTY[CONTACTZIP][1] = 123456
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
