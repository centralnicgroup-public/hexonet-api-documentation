# QueryDNSZoneList

## DESCRIPTION
Query a list of DNS Zones

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDNSZoneList` | COMMAND
WIDE | 1 | Return more properties than only the simple list of zones | `0`, `1` or `DNSNODE`
ORDERBY | 0 | Order list by defined algorithm, possible values are `DNSZONE`, `CREATEDDATE`, `UPDATEDDATE`, `EXPIRATIONDATE`, `QUERY-QUOTA-PREDICTION`, `QUERY-QUOTA-COUNT`, `QUERY-QUOTA-STATUS` | TEXT
FIRST | 0 | Parameter to implement a pagination, first will be the start of the list returned | INT
LIMIT | 0 | Limit the number of zones returned | INT
USERDEPTH | 0 | Userdepth allows to limit the list inside the usertree | `SELF`, `SUBUSER` or `ALL`
DNSZONE | 0 | Allows to use a zone name as search pattern | PATTERN or TEXT
SUBCLASS | 0 | Allows to filter the list for MASTER / SLAVE zones, can be set to `MASTER`, `SLAVE` | TEXT or NULL
SOAMNAME | 0 | Search by SOAMNAME | TEXT or NULL
MINCREATEDDATE | 0 | Filter by lowest CREATEDDATE | NULL or TEXT
MAXCREATEDDATE | 0 | Filter by highest CREATEDDATE | NULL or TEXT
MINUPDATEDDATE | 0 | Filter by lowest UPDATEDDATE | NULL or TEXT
MAXUPDATEDDATE | 0 | Filter by highest UPDATEDDATE | NULL or TEXT
MINEXPIRATIONDATE | 0 | Filter by lowest EXPIRATIONDATE | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Filter by highest EXPIRATIONDATE | NULL or TEXT
STATUS | 0 | Filter list by STATUS of DNSZONE | `ACTIVE`, `INACTIVE`, `HOLD` or NULL
PROPERTIES | 0 | Additional properties to be returned can be specified here. Currently supported values are:<br>`PREMIUMDNS` | TEXT or NULL
PREMIUMDNSCLASS | 0 | Only show objects with a PremiumDNS class that matches the pattern specified here. | PATTERN or TEXT
PREMIUMDNSCLASSREGEX | 0 | Only show objects with a PremiumDNS class that matches the regular expression specified here. | REGEX or NULL
PREMIUMDNSCLASSREGEXNOT | 0 | Only show objects with a PremiumDNS class that does not match the regular expression specified here. | REGEX or NULL
MINQUERY-QUOTA-COUNT | 0 | Filter by lowest QUERY-QUOTA-COUNT | INT
MAXQUERY-QUOTA-COUNT | 0 | Filter by highest QUERY-QUOTA-COUNT | INT
MINQUERY-QUOTA-PREDICTION | 0 | Filter by lowest QUERY-QUOTA-PREDICTION | INT
MAXQUERY-QUOTA-PREDICTION | 0 | Filter by highest QUERY-QUOTA-PREDICTION | INT
QUERY-QUOTA-STATUS | 0 | Filter by QUERY-QUOTA-STATUS, e.g. `OK`, `WARNING`, `EXCEEDED`, `SUSPENDED` | TEXT or NULL


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
FIRST | 1 | 1 | Returns the FIRST value submitted in the initial request | INT
LAST | 1 | 1 | Returns the LAST value submitted in the initial request | INT
COUNT | 1 | 1 | Number of zones returned in the list response | INT
TOTAL | 1 | 1 | Total number of zones (not only filtered zones!) | INT
LIMIT | 1 | 1 | Returns the LIMIT submitted in the initial request | INT
DNSZONE[0..N] | 0 | N | DNSZONE name | TEXT
DNSZONECONFIGCLASS[0..N] | 0 | N | Currently unused property | TEXT
DNSZONECREATEDDATE[0..N] | 0 | N | CREATEDDATE of the respective zone | DATE
DNSZONERRSTOTAL[0..N] | 0 | N | Total number of resource records inside the respective zone | INT
DNSZONESOAEXPIRE[0..N] | 0 | N | SOAEXPIRE of the respective zone | INT
DNSZONESOAMINTTL[0..N] | 0 | N | SOAMINTTL of the respective zone | INT
DNSZONESOAMNAME[0..N] | 0 | N | SOAMNAME of the respective zone | TEXT
DNSZONESOAREFRESH[0..N] | 0 | N | SOAREFRESH of the respective zone | INT
DNSZONESOARETRY[0..N] | 0 | N | SOARETRY of the respective zone | INT
DNSZONESOARNAME[0..N] | 0 | N | SOARNAME of the respective zone | TEXT
DNSZONESOASERIAL[0..N] | 0 | N | Value that indicates the "actuality" of the SOA-Record to other nameservers | INT
DNSZONESOATTL[0..N] | 0 | N | SOATTL value of the respective zone | INT
DNSZONESUBCLASS[0..N] | 0 | N | SUBCLASS of the respective zone | TEXT
DNSZONEUMLAUT[0..N] | 0 | N | UMLAUT version of DNSZONE | TEXT
DNSZONEUPDATEDDATE[0..N] | 0 | N | UPDATEDDATE of the respective zone | DATE
PARENTUSER[0..N] | 0 | N | Parentuser of the zone owner | TEXT
PEERUSER[0..N] | 0 | N | Subuserchain of the respective zone | TEXT
STATUS[0..N] | 0 | N | Status of the respective zone | TEXT
USER[0..N] | 0 | N | Owner of the respective zone | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDNSZoneList
LIMIT = 2
MAXCREATEDDATE = 2016-06-15
MINCREATEDDATE = 2012-01-01
SUBCLASS = external
USERDEPTH = self
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
PROPERTY[TOTAL][0] = 602
PROPERTY[LIMIT][0] = 2
PROPERTY[DNSZONE][0] = test123.de.
PROPERTY[DNSZONE][1] = estdomain.org.
PROPERTY[DNSZONECONFIGCLASS][0] =
PROPERTY[DNSZONECONFIGCLASS][1] =
PROPERTY[DNSZONECREATEDDATE][0] = 2012-01-05 17:22:28
PROPERTY[DNSZONECREATEDDATE][1] = 2012-01-30 05:46:11
PROPERTY[DNSZONERRSTOTAL][0] = 3
PROPERTY[DNSZONERRSTOTAL][1] = 3
PROPERTY[DNSZONESOAEXPIRE][0] = 3600000
PROPERTY[DNSZONESOAEXPIRE][1] = 3600000
PROPERTY[DNSZONESOAMINTTL][0] = 172800
PROPERTY[DNSZONESOAMINTTL][1] = 172800
PROPERTY[DNSZONESOAMNAME][0] = ns1.ispapi.net.
PROPERTY[DNSZONESOAMNAME][1] = ns1.ispapi.net.
PROPERTY[DNSZONESOAREFRESH][0] = 86400
PROPERTY[DNSZONESOAREFRESH][1] = 86400
PROPERTY[DNSZONESOARETRY][0] = 7200
PROPERTY[DNSZONESOARETRY][1] = 7200
PROPERTY[DNSZONESOARNAME][0] = hostmaster.test123.de.
PROPERTY[DNSZONESOARNAME][1] = hostmaster.estdomain.org.
PROPERTY[DNSZONESOASERIAL][0] = 2012010500
PROPERTY[DNSZONESOASERIAL][1] = 2012013000
PROPERTY[DNSZONESOATTL][0] = 3600
PROPERTY[DNSZONESOATTL][1] = 3600
PROPERTY[DNSZONESUBCLASS][0] = EXTERNAL
PROPERTY[DNSZONESUBCLASS][1] = EXTERNAL
PROPERTY[DNSZONEUMLAUT][0] = test123.de.
PROPERTY[DNSZONEUMLAUT][1] = estdomain.org.
PROPERTY[DNSZONEUPDATEDDATE][0] = 2012-01-05 17:22:28
PROPERTY[DNSZONEUPDATEDDATE][1] = 2012-01-30 05:46:11
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS][1] = ACTIVE
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
