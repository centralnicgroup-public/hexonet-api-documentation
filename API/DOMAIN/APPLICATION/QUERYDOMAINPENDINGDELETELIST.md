# QueryDomainPendingDeleteList

## DESCRIPTION
Query a detailed list of all backorder applications

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainPendingDeleteList` | COMMAND
KEYWORD[0..N] | 0 | Filter by a list of keywords | TEXT or NULL
KEYWORDCATENATION | 0 | Keyword concatenation. Can be `AND` or `OR` | `AND`, `OR` or NULL
KEYWORDMATCH | 0 | Specify which part of the domain name the keyword has to match. Can be `BEGIN`, `END` or `ANY` | `BEGIN`, `END`, `ANY` or NULL
ZONE[0..N] | 0 | Filter by zone | TEXT or NULL
DELETIONDAY[0..N] | 0 | Filter by deletion days | DATE or NULL
FINALIZATIONDATE[0..N] | 0 | Filter by finalization dates | DATE or NULL
MINFINALIZATIONDATE | 0 | Returns only results >= MINFINALIZATIONDATE | DATETIME or NULL
MAXFINALIZATIONDATE | 0 | Returns only results <= MAXFINALIZATIONDATE | DATETIME or NULL
LENGTH[0..N] | 0 | Filter by length of domain name (range: 1-20) | TEXT or NULL
SCORE[0..N] | 0 | Filter by score of domain names (range: 1-10) | TEXT or NULL
FILTER[0..N] | 0 | Filter by domain name criteria, must be one of the following:<br>`NOHYPHENS` show only domain names with no hyphens<br>`NONUMBERS`: show only domain names which don't contain any numbers<br>`NOIDNS` don't show any IDNs | `NOHYPHENS`, `NONUMBERS`, `NOIDNS` or NULL
ORDERBY | 0 | Parameter by which the output will sorted.<br>Must be one of the following:<br> `NAME`, `DELETIONDAY`, `FINALIZATIONDATE`, `SCORE`, `NAMEDESC`, `DELETIONDAYDESC`, `FINALIZATIONDATEDESC`, `SCOREDESC` or `RANDOM` | `NAME`, `DELETIONDAY`, `FINALIZATIONDATE`, `SCORE`, `NAMEDESC`, `DELETIONDAYDESC`, `FINALIZATIONDATEDESC`, `SCOREDESC`, `RANDOM` or NULL
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT or NULL
FIRST | 0 |  Index of the first entry to be returned | INT or NULL
REGEXP | 0 | Regular expression to match label. For example, the following matches labels which consist of digits only: `REGEXP = ^[0-9]+$` | LONGTEXT

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
COLUMN[0..N] | 0 | N | List of properties that will be returned | TEXT
DOMAIN[0..N] | 0 | N | Domain name | TEXT
FINALIZATIONDATE[0..N] | 0 | N | Finalization date of the domain name| TEXT
SCORE[0..N] | 0 | N | Score of the domain name | TEXT
SUBCLASS[0..N] | 0 | N | Sub class of returned domain | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainPendingDeleteList
LIMIT = 2
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
PROPERTY[TOTAL][0] = 535933
PROPERTY[LIMIT][0] = 2
PROPERTY[COLUMN][0] = DOMAIN
PROPERTY[COLUMN][1] = FINALIZATIONDATE
PROPERTY[COLUMN][2] = SCORE
PROPERTY[COLUMN][3] = SUBCLASS
PROPERTY[DOMAIN][0] = 0--l.com
PROPERTY[DOMAIN][1] = 0-2.co
PROPERTY[FINALIZATIONDATE][0] = 2016-08-20 17:00:00
PROPERTY[FINALIZATIONDATE][1] = 2016-08-18 16:00:00
PROPERTY[SCORE][0] = 0
PROPERTY[SCORE][1] = 7
PROPERTY[SUBCLASS][0] = COM
PROPERTY[SUBCLASS][1] = CO
EOF
```

----
