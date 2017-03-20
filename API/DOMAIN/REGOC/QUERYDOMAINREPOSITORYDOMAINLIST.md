# QueryDomainRepositoryDomainList

## DESCRIPTION
This command allows to get a list of the domain names, related to a given repository.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainRepositoryDomainList` | COMMAND
REPOSITORY | 1 | Repository name | TEXT
ZONE | 0 | Limit the query with the domain names under the given zone | TEXT or NULL
MINDATE | 0 | Limit the query with the minimal domain creation date | DATE or NULL
MAXDATE | 0 | Limit the query with the maximal domain creation date | DATE or NULL
FIRST | 0 | Response list offset | INT or NULL
LIMIT | 0 | Response list length limit | INT or NULL
ORDERBY | 0 | Sort the response list according to:<br>`CREATEDDATE` - domain creation date<br>`EXPIRATIONDATE` - domain expiration date<br>`UPDATEDDATE` - last domain update date<br>`TRANSFERDATE` - last domain transfer date<br>`DOMAIN` - domain name | TEXT or NULL

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
506 | Invalid option value
530 | Authentication failed
541 | Invalid attribute value
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | Index of the first item in the response list | INT
LAST | 1 | 1 | Index of the last item in the response list | INT
COUNT | 1 | 1 | Response list length | INT
TOTAL | 1 | 1 | Total number of records, returned by the query | INT
LIMIT | 1 | 1 | Response list length limit | INT
CREATEDDATE[0..N] | 0 | N | Domain creation date | DATETIME
DOMAIN[0..N] | 0 | N | Domain name | TEXT
EXPIRATIONDATE[0..N] | 0 | N | Domain expiration date | DATETIME
TRANSFERDATE[0..N] | 0 | N | Date of the last domain transfer | DATETIME
UPDATEDDATE[0..N] | 0 | N | Date of the last domain update | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainRepositoryDomainList
LIMIT = 2
MAXDATE = 2015-12-31
MINDATE = 2015-01-01
ORDERBY = DOMAIN
REPOSITORY = ITEPP-OTE-1API1
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
PROPERTY[TOTAL][0] = 25
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2015-05-29 09:43:55
PROPERTY[CREATEDDATE][1] = 2015-06-08 09:50:07
PROPERTY[DOMAIN][0] = alsetta3.it
PROPERTY[DOMAIN][1] = cirotel.it
PROPERTY[EXPIRATIONDATE][0] = 2017-05-29 21:59:59
PROPERTY[EXPIRATIONDATE][1] = 2017-06-08 21:59:59
PROPERTY[TRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[TRANSFERDATE][1] = 0000-00-00 00:00:00
PROPERTY[UPDATEDDATE][0] = 2016-04-12 15:17:59
PROPERTY[UPDATEDDATE][1] = 2015-06-08 09:50:06
EOF
```

----
