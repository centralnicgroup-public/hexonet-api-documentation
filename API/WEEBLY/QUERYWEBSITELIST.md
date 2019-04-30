# QueryWebsiteList

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryWebsiteList` | COMMAND
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
WEBSITEUSERID | 0 | ID of WebsiteUser  | INT
WIDE | 0 | If set to `1`: verbose output | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned | INT
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`USER`, `USERDESC`, `WEBSITEUSERID`, `WEBSITEUSERIDDESC`, `CLASS`, `CLASSDESC`, `FAILUREDATE`, `FAILUREDATEDESC`, `DESCRIPTION`, `DESCRIPTIONDESC`, `CREATEDDATE`, `CREATEDDATEDESC`, `PAIDUNTILDDATE`, `PAIDUNTILDATEDESC` | TEXT
USER | 0 | Show only websites which are assigned to a certain user | PATTERN or TEXT
STATUS | 0 | Only show websites with a status that matches the pattern specified here | PATTERN
CLASS | 0 | Only show websites with a class that matches the pattern specified here | PATTERN
CLASSREGEX | 0 | Only show objects where the class matches the regular expression specified here | REGEX or NULL
STATUS | 0 | Only show websites with a status that matches the pattern specified here | PATTERN
STATUSREGEX | 0 | Only show objects where the status matches the regular expression specified here | REGEX or NULL
DESCRIPTION | 0 | Only show websites with a description that matches the pattern specified here | PATTERN
DESCRIPTIONREGEX | 0 | Only show objects where the description matches the regular expression specified here | REGEX or NULL

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


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
CLASS[0..N] | 0 | N | Class of the website | TEXT
CREATEDDATE[0..N] | 0 | N | Creation date of the website | DATETIME
DESCRIPTION[0..N] | 0 | N | The respective URL of the website | TEXT
EXPIRATIONDATE[0..N] | 0 | N | Expiration date of website | DATETIME
FAILUREDATE[0..N] | 0 | N | Failure date of the website | DATETIME
OBJECTID[0..N] | 0 | N | The respective ID of the website | TEXT
PAIDUNTILDATE[0..N] | 0 | N | Paid until date of the website | DATETIME
RENEWALMODE[0..N] | 0 | N | Renewal mode of the website | TEXT
STATUS[0..N] | 0 | N | Status of the website | TEXT
UPDATEDDATE[0..N] | 0 | N | Last modification date of the website | DATETIME
USER[0..N] | 0 | N |  The user ID that the object belongs to | TEXT

## Example

### Command

```
[COMMAND]
command = QueryWebsiteList
orderby = CLASS
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2018-12-11 09:41:53
PROPERTY[CREATEDDATE][1] = 2018-12-11 09:43:53
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS][1] = PENDINGDELETE
PROPERTY[PAIDUNTILDATE][0] = 2019-12-11 09:41:53
PROPERTY[PAIDUNTILDATE][1] = 2019-12-11 09:43:53
PROPERTY[FAILUREDATE][0] = 2019-12-10 09:41:53
PROPERTY[FAILUREDATE][1] = 2019-12-10 09:43:53
PROPERTY[RENEWALMODE][0] = renew
PROPERTY[RENEWALMODE][1] = renew
PROPERTY[COUNT][0] = 2
PROPERTY[USER][0] = karches-weebly
PROPERTY[USER][1] = karches-weebly
PROPERTY[LAST][0] = 1
PROPERTY[LIMIT][0] = 10000
PROPERTY[CLASS][0] = WEEBLY_FREE
PROPERTY[CLASS][1] = WEEBLY_STARTER
PROPERTY[EXPIRATIONDATE][0] = 2019-12-11 09:41:53
PROPERTY[EXPIRATIONDATE][1]= 2019-12-11 09:43:53
PROPERTY[UPDATEDDATE][0] =
PROPERTY[UPDATEDDATE][1] =
PROPERTY[TOTAL][0] = 2
PROPERTY[FIRST][0] = 0
PROPERTY[OBJECTID][0] = 969057925419306716
PROPERTY[OBJECTID][1] = 186067701775539899
PROPERTY[DESCRIPTION][0] = www.w-free1.com
PROPERTY[DESCRIPTION][1] = www.w-starter1.com
EOF
```

----
