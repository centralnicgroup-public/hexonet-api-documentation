# QueryDomainAddonList

## DESCRIPTION
This command returns a list of all domains that have a specific domain addon enabled.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainAddonList` | COMMAND
ADDONCLASS | 1 | The addon class | TEXT
ADDONID | 0 | Filter by a specific addon ID. You can specify several addon IDs separated by a '/'. If no addon ID is specified all addon IDs of the addon class will be taken | TEXT
REPOSITORY | 0 | Filter by a specific domain repository | TEXT
DOMAIN | 0 | Filter by a specific domain | TEXT or NULL
APPLICANTNAME | 0 | Filter by domain owner's name | TEXT or NULL
STATUS | 0 | Filter by the status of the domain addon | TEXT
STATS | 0 | Set to `1` to generate additional statistics | `0`, `1` or NULL
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | The parameter by which the output will be sorted. <br>Must be one of the following:<br> `CREATEDDATECREATEDDATE`, `CREATEDDATEDESC`, `EXPIRATIONDATE`, `EXPIRATIONDATEDESC`, `STATUS`, `STATUSDESC`, `DOMAIN`, `DOMAINDESC`, `ADDONID`, `ADDONIDDESC` | TEXT
MINDATE | 0 | The minimal date when the addon was added for the respective domain | TEXT
MAXDATE | 0 | The maximal date when the addon was added for the respective domain | TEXT

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
540 | Attribute value is not unique
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
ADDONCLASS[0..N] | 0 | N | The respective domain class | TEXT
ADDONID[0..N] | 0 | N | The respective addon ID | TEXT
APPLICANTCITY[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's city | TEXT
APPLICANTCOUNTRY[0..N] | 0 | N | The domain owner's country | TEXT
APPLICANTEMAIL[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's email address | TEXT
APPLICANTFAX[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's fax number | TEXT
APPLICANTNAME[0..N] | 0 | N | The domain owner's name | TEXT
APPLICANTORGANIZATION[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's organization | TEXT
APPLICANTPHONE[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's phone number | TEXT
APPLICANTSTATE[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's state | TEXT
APPLICANTSTREET[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's street | TEXT
APPLICANTZIP[0..N] | 0 | N | Only returned if a specific domain is stated in the command: The domain owner's ZIP | TEXT
CREATEDDATE[0..N] | 0 | N | The creation date of the addon for the respective domain name | DATETIME
DOMAIN[0..N] | 0 | N | The respective domain name | TEXT
EXPIRATIONDATE[0..N] | 0 | N | The expiration date of the addon for the respective domain name | DATETIME
INUSE[0..N] | 0 | N | Indicates if the addon is in use for the domain name (`1`) or not (`0`) | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
REPOSITORY[0..N] | 0 | N | The respective domain repository | TEXT
STATUS[0..N] | 0 | N | The status of the addon for the respective domain | TEXT
SUMADDONREQUESTED | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "REQUESTED" | INT
SUMADDONNEW | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "NEW" | INT
SUMADDONCONFIRMED | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "CONFIRMED" | INT
SUMADDONDELETE | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "DELETE" | INT
SUMADDONCANCEL | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "CANCEL" | INT
SUMADDONEXPIRE | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "EXPIRE" | INT
SUMADDONHOLD | 0 | 1 | Only displayed if STATS is set to `1`: Sum of domains with addon status "HOLD" | INT
TOTAL | 0 | 1 | Only displayed if STATS is set to `1`: Total number of domains with addon | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainAddonList
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
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 24
PROPERTY[LIMIT][0] = 2
PROPERTY[ADDONCLASS][0] = PROXY
PROPERTY[ADDONCLASS][1] = PROXY
PROPERTY[ADDONID][0] = WHOISTRUSTEE_BIZ
PROPERTY[ADDONID][1] = WHOISTRUSTEE_BIZ
PROPERTY[APPLICANTCOUNTRY][0] = CA
PROPERTY[APPLICANTCOUNTRY][1] = CA
PROPERTY[APPLICANTNAME][0] = EQQY GROUP
PROPERTY[APPLICANTNAME][1] = Gonzalo Canales
PROPERTY[CREATEDDATE][0] = 2011-09-28 18:24:36
PROPERTY[CREATEDDATE][1] = 2012-05-08 09:20:08
PROPERTY[DOMAIN][0] = georgehsu.biz
PROPERTY[DOMAIN][1] = 65cgtde.biz
PROPERTY[EXPIRATIONDATE][0] = 2016-12-01 18:24:34
PROPERTY[EXPIRATIONDATE][1] = 2016-12-10 21:20:08
PROPERTY[INUSE][0] = 1
PROPERTY[INUSE][1] = 1
PROPERTY[PEERUSER][0] = demo.hexonet.net eqdomains
PROPERTY[PEERUSER][1] = demo.hexonet.net thetestaccount
PROPERTY[REPOSITORY][0] = BIZ-OTE-1API1
PROPERTY[REPOSITORY][1] = BIZ-OTE-1API1
PROPERTY[STATUS][0] = NEW
PROPERTY[STATUS][1] = NEW
EOF
```

----
