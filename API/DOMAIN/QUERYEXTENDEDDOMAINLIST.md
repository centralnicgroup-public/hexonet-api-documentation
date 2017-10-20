# QueryExtendedDomainList

## DESCRIPTION
Query a list of domains, along with several additional information parameters.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryExtendedDomainList` | COMMAND
WIDE | 0 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | The parameter by which the output will be sorted. <br>Must be one of the following:<br>`DOMAIN`, `DOMAINDESC`, `SUBCLASS`, `SUBCLASSDESC`, `USER`, `USERDESC`, `CREATEDDATE`, `CREATEDDATEDESC`, `UPDATEDDATE`, `UPDATEDDATEDESC`, `REGISTRATIONEXPIRATIONDATE`, `REGISTRATIONEXPIRATIONDATEDESC`, `REGISTRAR`, `REGISTRARDESC`, `EXPIRATIONDATE`, `EXPIRATIONDATEDESC`, `PAIDUNTILDATE`, `PAIDUNTILDATEDESC`, `NEXTACTIONDATE`, `NEXTACTIONDATEDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
ASSIGNED | 0 | Shows either all assigned or all unassigned (pending transfer/trades) domains (may be `0` or `1`) | `0` or `1`
DOMAIN | 0 | Filter output for domains which match the pattern specified here, e. g. `*.com`, `a*.de` | PATTERN or TEXT
DOMAINSUBCLASS | 0 | Show only domains with these subclasses, e.g. `COM` for .com domains | NULL or TEXT
OWNERCONTACT | 0 | Search for: Owner/Registrant-Contact | PATTERN
ADMINCONTACT | 0 | Search for: Admin-Contact | PATTERN
TECHCONTACT | 0 | Search for: Tech-Contact | PATTERN
BILLINGCONTACT | 0 | Search for: Billing-Contact | PATTERN
NAMESERVER | 0 | Search for: Nameserver | PATTERN
STATUS | 0 | Search for: domain status | PATTERN
MINCREATEDDATE | 0 | Search for: Minimal creating date | NULL or TEXT
MAXCREATEDDATE | 0 | Search for: Maximal creating date | NULL or TEXT
MINUPDATEDDATE | 0 | Search for: Minimal update date | NULL or TEXT
MAXUPDATEDDATE | 0 | Search for: Maximal update date | NULL or TEXT
MINREGISTRATIONEXPIRATIONDATE | 0 | Search for: Minimal registration expiration date | NULL or TEXT
MAXREGISTRATIONEXPIRATIONDATE | 0 | Search for: Maximal registration expiration date | NULL or TEXT
MINTRANSFERDATE | 0 | Only list domains which have been transferred after the date specified here | NULL or TEXT
MAXTRANSFERDATE | 0 | Only list domains which have been transferred before the date specified here | NULL or TEXT
X-TRUSTEE | 0 | Only list domains which have a Trustee Service enabled (`1`) or disabled (`0`) | NULL, `1` or `0`
RENEWALMODE | 0 | Only list domains with a certain renewal mode. Must be `EXPIRE`, `DELETE` or `RENEW` | NULL or TEXT

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
506 | Invalid option value
530 | Authentication failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry| INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
ASSIGNED[0..N] | 0 | N | Shows if the domain is assigned or not (`1` or `0`) | NULL, `1` or `0`
DNSZONE[0..N] | 0 | N | Shows if the domain also has a DNS zone | NULL, `1` or `0`
DNSZONECONFIGCLASS[0..N] | 0 | N | The config class of the DNS zone| TEXT
DNSZONEWWWTARGETDATA[0..N] | 0 | N | If a DNS zone exists to the domain, this shows the target of the URL | TEXT
DNSZONEWWWTARGETTYPE[0..N] | 0 | N | The type of target (e.g. `A`) configured in the DNS zone of the domain | TEXT
DOMAIN[0..N] | 0 | N | The domain name | TEXT
DOMAINACCOUNTINGDATE[0..N] | 0 | N | The date when the renewal accounting will get created | DATETIME
DOMAINADMINCONTACT[0..N] | 0 | N | The Administrative Contact | TEXT
DOMAINAUTH[0..N] | 0 | N | Authorization code of the domain | TEXT
DOMAINBILLINGCONTACT[0..N] | 0 | N | The Billing Contact | TEXT
DOMAINCONFIGCLASS[0..N] | 0 | N | Shows the config class (e.g. `DE`) of a domain | TEXT
DOMAINCREATEDBY[0..N] | 0 | N | Registrar that created the contact | TEXT
DOMAINCREATEDDATE[0..N] | 0 | N | Creation date of the domain | DATETIME
DOMAINEXPIRATIONDATE[0..N] | 0 | N | The expiration date within our renewal system | DATETIME
DOMAINFAILUREDATE[0..N] | 0 | N | The failure date of the domain | DATETIME
DOMAINFINALIZATIONDATE[0..N] | 0 | N | The finalization date of the domain | DATETIME
DOMAINHOST[0..N] | 0 | N | String showing the hosts assigned to the domain | TEXT
DOMAININTERNALNAMESERVER[0..N] | 0 | N | String showing the internal nameservers of the domain | TEXT
DOMAINNAMESERVER[0..N] | 0 | N | String showing the nameservers of the domain | TEXT
DOMAINNAMESERVERN[0..N] | 0 | N | Shows the nameservers of the domain | TEXT
DOMAINNEXTACTION[0..N] | 0 | N | The next renewal action of the domain | TEXT
DOMAINNEXTACTIONDATE[0..N] | 0 | N | The date of the next action to be performed | DATETIME
DOMAINOWNERCONTACT[0..N] | 0 | N | The Registrant/Owner | TEXT
DOMAINPAIDUNTILDATE[0..N] | 0 | N | The date until the domain is paid | DATETIME
DOMAINPREPAIDPERIOD[0..N] | 0 | N | The prepaid period of the domain | TEXT
DOMAINREGISTRAR[0..N] | 0 | N | Current sponsoring registrar | TEXT
DOMAINREGISTRARTRANSFERDATE[0..N] | 0 | N | The last transfer date | DATIME
DOMAINREGISTRARUPDATEDDATE[0..N] | 0 | N | Last update of registrar | DATETIME
DOMAINREGISTRATIONEXPIRATIONDATE[0..N] | 0 | N | The registration expiration date | DATETIME
DOMAINRENEWALMODE | 0 | N | The domain's renewal mode | TEXT
DOMAINRENEWALPERIOD[0..N] | 0 | N | The renewal period of the domain | TEXT
DOMAINSTATUS[0..N] | 0 | N | Status of the domain | TEXT
DOMAINSUBCLASS[0..N] | 0 | N | The domain's subclass | TEXT
DOMAINTECHCONTACT[0..N] | 0 | N | The Technical Contact | TEXT
DOMAINTRANSFERDATE[0..N] | 0 | N | The transfer date of domain | DATETIME
DOMAINTRANSFERLOCK[0..N] | 0 | N | Shows if a transferlock is active or not | NULL, `1` or `0`
DOMAINUMLAUT[0..N] | 0 | N | Shows the domain written in IDN | TEXT
DOMAINUPDATEDBY[0..N] | 0 | N | Registrar that updated the domain | TEXT
DOMAINUPDATEDDATE[0..N] | 0 | N | Last modification date of the domain | DATETIME
PARENTUSER[0..N] | 0 | N | The parent user ID | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
TRANSFER[0..N] | 0 | N | Shows if the list entry is a domain (`0`) or a transfer (`1`) | NULL, `1` or `0`
USER[0..N] | 0 | N | The user ID | TEXT
X-EXPIRED[0..N] | 0 | N | Indicates if a domain name has already expired | NULL, `1` or `0`

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryExtendedDomainList
LIMIT = 2
MAXCREATEDDATE = 2016-10-25 15:55:03
MINCREATEDDATE = 2016-10-20 15:55:03
STATUS = ACTIVE
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
PROPERTY[TOTAL][0] = 8
PROPERTY[LIMIT][0] = 2
PROPERTY[ASSIGNED][0] = 1
PROPERTY[ASSIGNED][1] = 1
PROPERTY[DNSZONE][0] = 1
PROPERTY[DNSZONE][1] = 1
PROPERTY[DNSZONECONFIGCLASS][0] =
PROPERTY[DNSZONECONFIGCLASS][1] =
PROPERTY[DNSZONEWWWTARGETDATA][0] =
PROPERTY[DNSZONEWWWTARGETDATA][1] =
PROPERTY[DNSZONEWWWTARGETTYPE][0] =
PROPERTY[DNSZONEWWWTARGETTYPE][1] =
PROPERTY[DOMAIN][0] = hx-as-test1.cafe
PROPERTY[DOMAIN][1] = hx-as-test1.store
PROPERTY[DOMAINACCOUNTINGDATE][0] = 2017-10-25 11:07:05
PROPERTY[DOMAINACCOUNTINGDATE][1] = 2017-10-24 23:59:59
PROPERTY[DOMAINADMINCONTACT][0] = P-TUH1260830
PROPERTY[DOMAINADMINCONTACT][1] = P-TUH1260830
PROPERTY[DOMAINAUTH][0] = q6V:aYuouPGG
PROPERTY[DOMAINAUTH][1] = 2D:HCDh2Zv0t
PROPERTY[DOMAINBILLINGCONTACT][0] = P-TUH1260830
PROPERTY[DOMAINBILLINGCONTACT][1] = P-TUH1260830
PROPERTY[DOMAINCONFIGCLASS][0] =
PROPERTY[DOMAINCONFIGCLASS][1] =
PROPERTY[DOMAINCREATEDBY][0] = SYSTEM
PROPERTY[DOMAINCREATEDBY][1] = SYSTEM
PROPERTY[DOMAINCREATEDDATE][0] = 2016-10-24 11:07:05
PROPERTY[DOMAINCREATEDDATE][1] = 2016-10-24 11:07:07
PROPERTY[DOMAINEXPIRATIONDATE][0] = 2017-10-24 11:07:05
PROPERTY[DOMAINEXPIRATIONDATE][1] = 2017-10-24 23:59:59
PROPERTY[DOMAINFAILUREDATE][0] = 2017-12-07 11:07:05
PROPERTY[DOMAINFAILUREDATE][1] = 2017-12-07 23:59:59
PROPERTY[DOMAINFINALIZATIONDATE][0] = 2017-11-28 11:07:05
PROPERTY[DOMAINFINALIZATIONDATE][1] = 2017-12-07 23:59:59
PROPERTY[DOMAINHOST][0] =
PROPERTY[DOMAINHOST][1] =
PROPERTY[DOMAININTERNALNAMESERVER][0] = ns1.ispapi.net ns2.ispapi.net
PROPERTY[DOMAININTERNALNAMESERVER][1] = ns1.ispapi.net ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER][0] = ns2.ispapi.net ns1.ispapi.net
PROPERTY[DOMAINNAMESERVER][1] = ns2.ispapi.net ns1.ispapi.net
PROPERTY[DOMAINNEXTACTION][0] = pay
PROPERTY[DOMAINNEXTACTION][1] = pay
PROPERTY[DOMAINNEXTACTIONDATE][0] = 2017-10-25 11:07:05
PROPERTY[DOMAINNEXTACTIONDATE][1] = 2017-10-24 23:59:59
PROPERTY[DOMAINOWNERCONTACT][0] = P-TUH1260830
PROPERTY[DOMAINOWNERCONTACT][1] = P-TUH1260830
PROPERTY[DOMAINPAIDUNTILDATE][0] = 2017-10-24 11:07:05
PROPERTY[DOMAINPAIDUNTILDATE][1] = 2017-10-24 23:59:59
PROPERTY[DOMAINPREPAIDPERIOD][0] = 0
PROPERTY[DOMAINPREPAIDPERIOD][1] = 0
PROPERTY[DOMAINREGISTRAR][0] = SYSTEM
PROPERTY[DOMAINREGISTRAR][1] = SYSTEM
PROPERTY[DOMAINREGISTRARTRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[DOMAINREGISTRARTRANSFERDATE][1] = 0000-00-00 00:00:00
PROPERTY[DOMAINREGISTRARUPDATEDDATE][0] = 2016-10-24 11:07:05
PROPERTY[DOMAINREGISTRARUPDATEDDATE][1] = 2016-10-24 11:07:06
PROPERTY[DOMAINRENEWALMODE][0] = renew
PROPERTY[DOMAINRENEWALMODE][1] = renew
PROPERTY[DOMAINRENEWALPERIOD][0] =
PROPERTY[DOMAINRENEWALPERIOD][1] =
PROPERTY[DOMAINSTATUS][0] = ACTIVE
PROPERTY[DOMAINSTATUS][1] = ACTIVE
PROPERTY[DOMAINSUBCLASS][0] = CAFE
PROPERTY[DOMAINSUBCLASS][1] = STORE
PROPERTY[DOMAINTECHCONTACT][0] = P-TUH1260830
PROPERTY[DOMAINTECHCONTACT][1] = P-TUH1260830
PROPERTY[DOMAINTRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[DOMAINTRANSFERDATE][1] = 0000-00-00 00:00:00
PROPERTY[DOMAINTRANSFERLOCK][0] = 0
PROPERTY[DOMAINTRANSFERLOCK][1] = 0
PROPERTY[DOMAINUMLAUT][0] = hx-as-test1.cafe
PROPERTY[DOMAINUMLAUT][1] = hx-as-test1.store
PROPERTY[DOMAINUPDATEDBY][0] = SYSTEM
PROPERTY[DOMAINUPDATEDBY][1] = SYSTEM
PROPERTY[DOMAINUPDATEDDATE][0] = 2016-10-24 11:07:05
PROPERTY[DOMAINUPDATEDDATE][1] = 2016-10-24 11:07:06
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[TRANSFER][0] = 0
PROPERTY[TRANSFER][1] = 0
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
PROPERTY[X-EXPIRED][0] =
PROPERTY[X-EXPIRED][1] =
EOF
```

----
