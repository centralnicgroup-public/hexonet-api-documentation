# QueryDomainRepositoryList

## DESCRIPTION
Queries a list of all domain repositories which belong to the executing user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainRepositoryList` | COMMAND
WIDE | 0 | If set to `1`: verbose output (more parameters) | `0`, `1` or NULL
SUBUSER | 0 | Only lists domain repositories for a specific subuser | TEXT or NULL
USERDEPTH | 0 | Depth of the list. Maybe `SELF` (only lists domain repositories which belong directly to the executing user) or `ALL` (lists domain repositories which belong the executing user's subusers as well). Default is `ALL`| `SELF` or `ALL`

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
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDDATE[0..N] | 0 | N | The creation date of the repository | DATETIME
REGISTRAR[0..N] | 0 | N | Name of the registrar that manages this repository | TEXT
REGISTRY[0..N] | 0 | N | Short name of the registry | TEXT
REGISTRYBILLINGMODUS[0..N] | 0 | N | The billing mode of the registry | TEXT
REGISTRYNAME[0..N] | 0 | N | Full name of the registry | TEXT
REPOSITORY[0..N] | 0 | N | Name of the repository | TEXT
STATUS[0..N] | 0 | N | Status of the repository | TEXT
STATUS_ACCOUNTING[0..N] | 0 | N | Indicates if the registry supports retrieving accounting information via an API for the repository | `1` or `0`
SUM_DOMAINS[0..N] | 0 | N | Sum of domains belonging to the respective repository | INT
TOTAL_DOMAINS | 1 | 1 | Total sum of domains which belong to repositories queried in the command | INT
UPDATEDDATE[0..N] | 0 | N | Last updated date | DATETIME
ZONES[0..N] | 0 | N | List of zones of the respective repository | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainRepositoryList
SUBUSER = johan.living.stone
USERDEPTH = ALL
WIDE = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2010-02-24 09:32:50
PROPERTY[CREATEDDATE][1] = 2008-11-14 13:40:02
PROPERTY[CREATEDDATE][2] = 2009-05-25 00:00:00
PROPERTY[REGISTRAR][0] = 1API
PROPERTY[REGISTRAR][1] = 1API
PROPERTY[REGISTRAR][2] = 1API
PROPERTY[REGISTRY][0] = CZ
PROPERTY[REGISTRY][1] = PL
PROPERTY[REGISTRY][2] = IIS
PROPERTY[REGISTRYBILLINGMODUS][0] =
PROPERTY[REGISTRYBILLINGMODUS][1] =
PROPERTY[REGISTRYBILLINGMODUS][2] = INVOICE
PROPERTY[REGISTRYNAME][0] = CZ.NIC
PROPERTY[REGISTRYNAME][1] = NASK
PROPERTY[REGISTRYNAME][2] = IIS
PROPERTY[REPOSITORY][0] = CZ-OTE-1API1
PROPERTY[REPOSITORY][1] = PL-OTE-1API1
PROPERTY[REPOSITORY][2] = SE-OTE-1API1
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS][1] = ACTIVE
PROPERTY[STATUS][2] = ACTIVE
PROPERTY[STATUS_ACCOUNTING][0] = 0
PROPERTY[STATUS_ACCOUNTING][1] = 1
PROPERTY[STATUS_ACCOUNTING][2] = 0
PROPERTY[SUM_DOMAINS][0] = 4253
PROPERTY[SUM_DOMAINS][1] = 781
PROPERTY[SUM_DOMAINS][2] = 971
PROPERTY[TOTAL_DOMAINS][0] = 6005
PROPERTY[UPDATEDDATE][0] = 2010-02-24 09:32:50
PROPERTY[UPDATEDDATE][1] = 2015-11-13 12:09:52
PROPERTY[UPDATEDDATE][2] = 2013-09-30 07:34:29
PROPERTY[ZONES][0] = cz
PROPERTY[ZONES][1] = biz.pl|com.pl|info.pl|net.pl|org.pl|pl|waw.pl
PROPERTY[ZONES][2] = a.se|ac.se|bd.se|c.se|d.se|e.se|f.se|g.se|h.se|i.se|k.se|l.se|m.se|n.se|o.se|org.se|p.se|parti.se|pp.se|press.se|r.se|s.se|se|t.se|tm.se|u.se|w.se|x.se|y.se|z.se
EOF
```

----
