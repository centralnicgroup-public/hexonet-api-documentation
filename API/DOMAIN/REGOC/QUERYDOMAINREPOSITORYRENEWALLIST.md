# QueryDomainRepositoryRenewalList

## DESCRIPTION
Query the sum of all executed transactions for a domain repository.

## AVAILABILITY
This command is only available for users who hold their own domain repository.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainRepositoryRenewalList` | COMMAND
REPOSITORY | 1 | Name of repository for which the command should be executed | TEXT
MINDATE | 1 | Date where the sum should start | TEXT
MAXDATE | 1 | Date where the sum should end | TEXT

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
SUM_CREATE[0..N] | 0 | N | Sum of domain creations | INT
SUM_DELETE[0..N] | 0 | N | Sum of domain deletions | INT
SUM_RENEW[0..N] | 0 | N | Sum of domain renewals | INT
SUM_UNCREATE[0..N] | 0 | N | Sum of domain un-creates | INT
SUM_UNRENEW[0..N] | 0 | N | Sum of redeemed renewals | INT
ZONES[0..N] | 0 | N | List of zones for the repository | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainRepositoryRenewalList
MAXDATE = 2016-11-15
MINDATE = 2016-11-14
REPOSITORY = ITEPP-OTE-1API1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[SUM_CREATE][0] = 0
PROPERTY[SUM_DELETE][0] = 2
PROPERTY[SUM_RENEW][0] = 15
PROPERTY[SUM_UNCREATE][0] = 0
PROPERTY[SUM_UNRENEW][0] = 0
PROPERTY[ZONES][0] = it
EOF
```

----
