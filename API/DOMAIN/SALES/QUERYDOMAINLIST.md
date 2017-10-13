# QueryDomainList

## DESCRIPTION
The QueryDomainList command version 2 can be used to obtain the DOMAINSALE properties.
Below are only the domain sales related parameters, the other parameters can be seen in
[API/DOMAIN/COMMON/QUERYDOMAINLIST_VERSION2.md](../COMMON/QUERYDOMAINLIST_VERSION2.md)


## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainList` | COMMAND
VERSION | 1 | Indicates the version of the command. To access this version 2 of QueryDomainsList, `2` must be use used as value | INT
PROPERTIES | 0 | The properties to return, e.g. `DOMAINSALE` | TEXT or NULL
DOMAINSALE-STATUS | 0 | Domain sale status | `NONE`, `DISABLED`, `REQUESTED` or `ACTIVE`
DOMAINSALE-SEDO-STATUS | 0 | Domain sale Sedo status | `NONE`, `DISABLED`, `REQUESTED` or `ACTIVE`
DOMAINSALE-AFTERNIC-STATUS | 0 | Domain sale AfterNIC status | `NONE`, `DISABLED`, `REQUESTED` or `ACTIVE`
DOMAINSALE-SEDO-LISTING-TYPE | 0 | Domain sale Sedo listing type | `MAKE_OFFER`, `BUY_NOW_STAGED` or `BUY_NOW_INSTANT`
DOMAINSALE-SEDO-LISTING-STATUS | 0 | Domain sale Sedo listing status | `ERROR`, `PENDING`, `LISTED` or `DECLINED`
DOMAINSALE-SEDO-MLS-LISTING-STATUS | 0 | Domain sale Sedo MLS listing status | `PENDING`, `LISTED` or `NOTLISTED`
MINDOMAINSALE-PRICE | 0 | Min sale price | `/^[0-9]+(\.[0-9]+)?$/`
MAXDOMAINSALE-PRICE | 0 | Max sale price | `/^[0-9]+(\.[0-9]+)?$/`
MINDOMAINSALE-SEDO-PRICE | 0 | Min Sedo sale price | `/^[0-9]+(\.[0-9]+)?$/`
MAXDOMAINSALE-SEDO-PRICE | 0 | Max Sedo sale price | `/^[0-9]+(\.[0-9]+)?$/`
MINDOMAINSALE-AFTERNIC-PRICE | 0 | Min AfterNIC sale price | `/^[0-9]+(\.[0-9]+)?$/`
MAXDOMAINSALE-AFTERNIC-PRICE | 0 | Max AfterNIC sale price | `/^[0-9]+(\.[0-9]+)?$/`


----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
549 | Channel error

Property | Min | Definition | Type
---- | ---- | ---- | ----
OBJECTID | 1 | The Object ID | TEXT
DESCRIPTION | 1 | The object description | TEXT
DOMAINSALE-AFTERNIC-STATUS | 0 | The AfterNIC listing status | `DISABLED`, `REQUESTED` or `ACTIVE`
DOMAINSALE-AFTERNIC-PRICE | 0 | The AfterNIC listing price | /^[0-9]+(\.[0-9]+)?$/
DOMAINSALE-SEDO-STATUS | 0 |  The AfterNIC listing status | `DISABLED`, `REQUESTED` or `ACTIVE`
DOMAINSALE-SEDO-PRICE | 0 | The Sedo listing price | /^[0-9]+(\.[0-9]+)?$/
DOMAINSALE-SEDO-MINPRICE | 0 | The Sedo minimum price | /^[0-9]+(\.[0-9]+)?$/
DOMAINSALE-SEDO-CURRENCY | 0 | The Sedo currency | `EUR`, `USD`, or `GBP`
DOMAINSALE-SEDO-LISTING-TYPE | 0 | The Sedo listing type | `buy_now_instant`, `buy_now_staged` or `make_offer`

----
## Example

### Command
To get the properties for a domain:
```
[COMMAND]
COMMAND = QueryDomainList
VERSION = 2
DOMAIN = test12345.com
PROPERTIES = DOMAINSALE
EOF
```
### Response

```
[RESPONSE]
PROPERTY[DOMAINSALE-SEDO-LISTING-TYPE][0]=buy_now_staged
PROPERTY[COUNT][0]=1
PROPERTY[LAST][0]=0
PROPERTY[LIMIT][0]=10000
PROPERTY[DOMAINSALE-AFTERNIC-STATUS][0]=ACTIVE
PROPERTY[DOMAINSALE-SEDO-STATUS][0]=ACTIVE
PROPERTY[DOMAINSALE-SEDO-MINPRICE][0]=0.00
PROPERTY[SUBCLASS][0]=DE
PROPERTY[DOMAINSALE-SEDO-CURRENCY][0]=EUR
PROPERTY[DOMAINSALE-AFTERNIC-PRICE][0]=299.00
PROPERTY[REPOSITORY][0]=DENIC-332
PROPERTY[DOMAINSALE-SEDO-PRICE][0]=299.00
PROPERTY[TOTAL][0]=1
PROPERTY[FIRST][0]=0
PROPERTY[OBJECTID][0]=a-job.de
PROPERTY[DESCRIPTION][0]=a-job.de
PROPERTY[OBJECTCLASS][0]=DOMAIN
DESCRIPTION=Command completed successfully
CODE=200
QUEUETIME=0
RUNTIME=0.023
EOF
```

### Command
To get all the domains of an user which are listed for price > 0:
```
xsc xirca-ote --USER=demo.hexonet.net QueryDomainList VERSION=2 MINDOMAINSALE-PRICE=0.01
```

----
