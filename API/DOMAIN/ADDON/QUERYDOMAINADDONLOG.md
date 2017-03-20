# QueryDomainAddonLog

## DESCRIPTION
This command queries a list of domain addon log entries.

## AVAILABILITY
All users have access to this command. This command only returns log entries for domain addons which the executing user owns.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainAddonLog` | COMMAND
ADDONCLASS | 1 | Addon class | TEXT
ADDONID | 0 | Filter by a specific addon ID. You can specify several addon IDs separated by a '/'. If no addon ID is specified all addon IDs of the addon class will be taken | TEXT
REPOSITORY | 0 | Filter by a specific domain repository. You can specify several repositories separated by a '/'. | TEXT
DOMAIN | 0 | Filter by a specific domain name | TEXT
ACTION | 0 | Filter by a specific action. <br> Must be one of the following: <br> `ACTIVATE`, `ADD_BLACKLIST`, `CONFIRM`, `UNCONFIRM`, `CREATE`, `UNCREATE`, `DEACTIVATE`, `DEL_BLACKLIST`, `CANCEL`, `DELETE`, `EXPIRE`, `PENDING`, `RENEW`, `COMMENT` | TEXT
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | The parameter by which the output will be sorted.<br> Must be one of the following: <br> `CREATEDDATE`, `CREATEDDATEDESC`, `LOGDATE`, `LOGDATEDESC`, `OPERATIONTYPE`, `OPERATIONTYPEDESC`, `STATUS`, `STATUSDESC`, `DOMAIN`, `DOMAINDESC` | TEXT
MINDATE | 0 | Minimal date of the log entry | TEXT
MAXDATE | 0 | Maximal date of the log entry | TEXT
ADDONMINAGE | 0 | The minimal age of the addon. Value has to be a dedicated number of months (e.g. `3M`) or years (e.g. `1Y`) | TEXT
ADDONMAXAGE | 0 | The maximal age of the addon. Value has to be a dedicated number of months (e.g. `3M`) or years (e.g. `1Y`) | TEXT
STATS | 0 | If set to `1` additional statistics will be displayed | `0`, `1` or NULL
PROPERTIES | 0 | You can specify additional properties to be returned. Only allowed value is `PRICE` | TEXT

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
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
ADDONCLASS[0..N] | 0 | N | The respective addon class | TEXT
ADDONID[0..N] | 0 | N | The respective addon ID | TEXT
COMMENT[0..N] | 0 | N | If available, a comment regarding the log entry | TEXT
CREATEDDATE[0..N] | 0 | N  | The creation date of the log entry | DATETIME
CURRENCY[0..N] | 0 | N | Only returned if PROPERTIES is set to `PRICE`: the respective currency of the creation/renewal price | TEXT
DOMAIN[0..N] | 0 | N  | The respective domain name which has the domain addon activated | TEXT
OPERATIONTYPE[0..N] | 0 | N | The operation type of the log entry | TEXT
PRICE[0..N] | 0 | N | Only returned if PROPERTIES is set to `PRICE`: the creation price of the domain addon | DECIMAL
RENEWALPERIOD[0..N] | 0 | N | The domain addon's renewal period | TEXT
RENEWALPRICE[0..N] | 0 | N | Only returned if PROPERTIES is set to `PRICE`: the renewal price of the domain addon | DECIMAL
SUMADDONLOGACTIVATE | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `ACTIVATE` | INT
SUMADDONLOGADDBLACKLIST | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `ADD_BLACKLIST` | INT
SUMADDONLOGCANCEL | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `CANCEL` | INT
SUMADDONLOGCONFIRM | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `CONFIRM` | INT
SUMADDONLOGCREATE | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `CREATE` | INT
SUMADDONLOGDEACTIVATE | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `DEACTIVATE` | INT
SUMADDONLOGDELBLACKLIST | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `DEL_BLACKLIST` | INT
SUMADDONLOGDELETE | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `DELETE` | INT
SUMADDONLOGEXPIRE | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `EXPIRE` | INT
SUMADDONLOGPENDING | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `PENDING` | INT
SUMADDONLOGRENEW | 0 | 1 | Only returned if stats is set to `1`: Sum of log entries with action `RENEW` | INT
TOTAL | 0 | 1 | Only returned if stats is set to `1`: Total number of log entries | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainAddonLog
ADDONCLASS = PROXY
ADDONID = WHOISTRUSTEE_BIZ
LIMIT = 2
REPOSITORY = BIZ-OTE-1API1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 429
PROPERTY[LAST][0] = 430
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 431
PROPERTY[LIMIT][0] = 2
PROPERTY[ADDONCLASS][0] = PROXY
PROPERTY[ADDONCLASS][1] = PROXY
PROPERTY[ADDONID][0] = WHOISTRUSTEE_BIZ
PROPERTY[ADDONID][1] = WHOISTRUSTEE_BIZ
PROPERTY[COMMENT][0] = renewal (period: 1M -> new expiration date: 2016-12-26 08:20:29)
PROPERTY[COMMENT][1] = renewal (period: 1M -> new expiration date: 2016-12-26 13:25:10)
PROPERTY[CREATEDDATE][0] = 2016-11-25 21:00:09
PROPERTY[CREATEDDATE][1] = 2016-11-26 02:00:07
PROPERTY[DOMAIN][0] = caru.biz
PROPERTY[DOMAIN][1] = milic5.biz
PROPERTY[OPERATIONTYPE][0] = RENEW
PROPERTY[OPERATIONTYPE][1] = RENEW
PROPERTY[RENEWALPERIOD][0] = 1M
PROPERTY[RENEWALPERIOD][1] = 1M
EOF
```

----
