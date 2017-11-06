# QueryDomainList

## DESCRIPTION
Query a list of domains.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainList` | COMMAND
WIDE | 0 | If set to `1`: verbose output | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned | INT
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`DOMAIN`, `DOMAINDESC`, `DOMAINSUBCLASS`, `DOMAINSUBCLASSDESC`, `USER`, `USERDESC`, `CREATEDDATE`, `CREATEDDATEDESC`, `UPDATEDDATE`, `UPDATEDDATEDESC`, `EXPIRATIONDATE`, `EXPIRATIONDATEDESC` `REGISTRATIONEXPIRATIONDATE`, `REGISTRATIONEXPIRATIONDATEDESC`, `PAIDUNTILDATE`, `PAIDUNTILDATEDESC`, `STATUS`, `STATUSDESC`, `REGISTRAR`, `REGISTRARDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
UNIQUE | 0 | If set to `1` only unique results will be returned | `1`, `0` or NULL
PROPERTIES | 0 | Additional properties to be returned can be specified here. Currently only supported value is `RENEWALPRICE` which returns additional information about the upcoming renewal of a domain name | TEXT or NULL
DOMAIN | 0 | Only show domains which match the pattern specified here | PATTERN or TEXT
DOMAINSUBCLASS | 0 | Only shows domains with a subclass specified here (syntax: `COM.` [beware the "." at the END of the TLD]) | NULL or TEXT
OWNERCONTACT | 0 | Only show domains which have a owner contact handle assigned that matches the pattern specified here | PATTERN
ADMINCONTACT | 0 | Only show domains which have a administrative contact handle assigned that matches the pattern specified here | PATTERN
TECHCONTACT | 0 | Only show domains which have a technical contact handle assigned that matches the pattern specified here | PATTERN
BILLINGCONTACT | 0 | Only show domains which have a billing contact handle assigned that matches the pattern specified here | PATTERN
NAMESERVER | 0 | Only show domains which have nameservers assigned that match the pattern specified here | PATTERN
NAMESERVER[0..N] | 0 | Only show domains which have one of the nameservers specified here assigned | TEXT or NULL
STATUS | 0 | Only show domains with a status that matches the pattern specified here | PATTERN
TRANSFERLOCK | 0 | Only show domains which have a transfer lock enabled (`1`) or disabled (`0`) | `0`, `1` or NULL
MINCREATEDDATE | 0 | Minimal creation date of returned domains | NULL or TEXT
MAXCREATEDDATE | 0 | Maximal creation date of returned domains | NULL or TEXT
MINUPDATEDDATE | 0 | Minimal updated date of returned domains | NULL or TEXT
MAXUPDATEDDATE | 0 | Maximal updated date of returned domains | NULL or TEXT
MINEXPIRATIONDATE | 0 | Minimal expiration date of returned domains | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Maximal expiration date of returned domains | NULL or TEXT
MINPAIDUNTILDATE | 0 | Minimal paid until date of returned domains | NULL or TEXT
MAXPAIDUNTILDATE | 0 | Maximal paid until date of returned domains | NULL or TEXT
MINREGISTRATIONEXPIRATIONDATE | 0 | Minimal registration expiration date of returned domains | NULL or TEXT
MAXREGISTRATIONEXPIRATIONDATE | 0 | Maximal registration expiration date of returned domains | NULL or TEXT
RENEWALMODE | 0 | Show only domains with a certain renewal mode.<br>Can be`EXPIRE`, `DELETE` or `RENEW` | NULL or TEXT
REPOSITORY | 0 | Show only domains which belong to a certain domain repository | NULL or TEXT
USER | 0 | Show only domains which are assigned to a certain user | PATTERN or TEXT
X-TRUSTEE | 0 | Set to `1` to only show domains which have a trustee (local presence service) activated | NULL, `1` or `0`
X-ACCEPT-WHOISTRUSTEE-TAC | 0 | Set to `1` to only show domains which have the Whois Trustee Service enabled | NULL, `1` or `0`
X-ACCEPT-WHOISTRUSTEELITE-TAC | 0 | Set to `1` to only show domains which have the Whois Trustee Lite Service enabled | NULL, `1` or `0`
X-MOBI-ACCEPT-INSTANTMOBILIZER-TAC | 0 | Set to `1` to only show domains which have the .MOBI Instant Mobilizer enabled | NULL, `1` or `0`

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
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
CURRENCY[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: currency of the upcoming renewal | TEXT
DOMAIN[0..N] | 0 | N | The respective domain name | TEXT
DOMAINACCOUNTINGDATE[0..N] | 0 | N | The accounting date of domain | DATETIME
DOMAINADMINCONTACT[0..N] | 0 | N | The administrative contact of the domain name | TEXT
DOMAINAUTH[0..N] | 0 | N | Authorization code of the domain name | TEXT
DOMAINBILLINGCONTACT[0..N] | 0 | N | The billing contact of the domain name | TEXT
DOMAINCONFIGCLASS[0..N] | 0 | N | Shows the configuration class (e.g. DE) of the domain | TEXT
DOMAINCREATEDBY[0..N] | 0 | N | Entity that created the domain | TEXT
DOMAINCREATEDDATE[0..N] | 0 | N | Creation date of the domain | DATETIME
DOMAINEXPIRATIONDATE[0..N] | 0 | N | Expiration date of the domain | DATETIME
DOMAINFAILUREDATE[0..N] | 0 | N | Failure date of the domain | DATETIME
DOMAINFINALIZATIONDATE[0..N] | 0 | N | Finalization date of the domain | DATETIME
DOMAININTERNALNAMESERVER[0..N] | 0 | N | A list of nameservers that are managed internally for the domain name, separated by spaces | TEXT
DOMAINNAMESERVER[0..N] | 0 | N | Nameserver assigned to the respective domain | TEXT
DOMAINNAMESERVER0..N[0..N] | 0 | N | List of nameservers assigned to the domain | TEXT
DOMAINNEXTACTION[0..N] | 0 | N  | Next action for the domain name. It can be:<br>`pay`: Only applies for RENEWALMODE: AUTORENEW. Before the ACCOUNTINGDATE, a payment from the domain's respective user account will be charged. If payment fails, the NEXTACTION remains "pay" for one more day. A second failed charge attempt changes NEXTACTION to `expireunpaid`.<br>`finalize`: Only applies for RENEWALMODE: AUTORENEW. After the ACCOUNTINGDATE and after a successful payment, the NEXTACTION is `finalize` (execute domain renewal) on the FINALIZATIONDATE. Please remember that on or after the FINALIZATIONDATE, a domain renewal cannot be stopped and no refunds are offered.<br>`expire`: Only applies for RENEWALMODE: AUTOEXPIRE. The NextAction is to transfer the domain to the respective registry on the FailureDate. Please note that this only applies to a handful of TLDs (e.g. .DE, .AT).<br>`expireunpaid`: Only applies for RENEWALMODE: AUTORENEW. If payment can not be charged on the ACCOUNTINGDATE, this action applies. As a result, on the FAILUREDATE for the domain, the domain is either deleted or transferred to the respective registry.<br>`delete`: This action applies only if RENEWALMODE: AUTODELETE. The domain will be deleted on its FAILUREDATE. | TEXT
DOMAINNEXTACTIONDATE[0..N] | 0 | N | Next action date of the domain | DATETIME
DOMAINOWNERCONTACT[0..N] | 0 | N | The Registrant/Owner contact of the domain name| TEXT
DOMAINPAIDUNTILDATE[0..N] | 0 | N | Paid until date of the domain name | DATETIME
DOMAINPREPAIDPERIOD[0..N] | 0 | N | Prepaid period of the domain name | TEXT
DOMAINREGISTRAR[0..N] | 0 | N | Current sponsoring registrar | TEXT
DOMAINREGISTRARTRANSFERDATE[0..N] | 0 | N | The last transfer date | DATETIME
DOMAINREGISTRARUPDATEDDATE[0..N] | 0 | N | The updated date of the registrar | DATETIME
DOMAINREGISTRATIONEXPIRATIONDATE[0..N] | 0 | N | The registration expiration date of the domain| DATETIME
DOMAINRENEWALMODE[0..N] | 0 | N | Renewal mode of the domain name | TEXT
DOMAINRENEWALPERIOD[0..N] | 0 | N | Renewal period of the domain name | TEXT
DOMAINREPOSITORY[0..N] | 0 | N | Repository the domain belongs to | TEXT
DOMAINSTATUS[0..N] | 0 | N | Status of the domain | TEXT
DOMAINSUBCLASS[0..N] | 0 | N | Subclass of the domain name | TEXT
DOMAINTECHCONTACT[0..N] | 0 | N | The technical contact of the domain | TEXT
DOMAINTRANSFERDATE[0..N] | 0 | N | The transfer date of domain | DATETIME
DOMAINTRANSFERLOCK[0..N] | 0 | N | Indicates if a transferlock is active or not | `1`, `0` or NULL
DOMAINUMLAUT[0..N] | 0 | N | Shows the domain written in IDN | TEXT
DOMAINUPDATEDBY[0..N] | 0 | N | Entity that updated the domain | TEXT
DOMAINUPDATEDDATE[0..N] | 0 | N | Last modification date of the domain | DATETIME
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
RENEWALPRICE[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: Price of the upcoming renewal not including taxes | DECIMAL
RENEWALGROSSPRICE[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: Gross price of the upcoming renewal | DECIMAL
USER[0..N] | 0 | N |  The user ID that the object belongs to | TEXT
VAT[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: VAT of the upcoming renewal | TEXT
X-ACCEPT-WHOISTRUSTEE-TAC[0..N] | 0 | N | Indicates if the Whois Trustee Service is enabled for the domain | `0`, `1` or NULL
X-ACCEPT-WHOISTRUSTEELITE-TAC[0..N] | 0 | N | Indicates if the Whois Trustee Service Lite is enabled for the domain | `0`, `1` or NULL
X-EXPIRED[0..N] | 0 | N | Indicates if a domain name is already expired | `0`, `1` or NULL
X-MOBI-ACCEPT-INSTANTMOBILIZER-TAC[0..N] | 0 | N | Indicates if the .MOBI Instant Mobilizer is enabled for the domain | `0`, `1` or NULL
X-TRUSTEE[0..N] | 0 | N | Indicates if a Trustee (local presence service) is activated for the domain | `0`, `1` or NULL
----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainList
LIMIT = 2
MAXCREATEDDATE = 2016-10-25 15:55:03
MINCREATEDDATE = 2016-10-20 15:55:03
STATUS = ACTIVE
TRANSFERLOCK = 0
UNIQUE = 1
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
PROPERTY[TOTAL][0] = 4
PROPERTY[LIMIT][0] = 2
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
PROPERTY[DOMAININTERNALNAMESERVER][0] = ns1.ispapi.net ns2.ispapi.net
PROPERTY[DOMAININTERNALNAMESERVER][1] = ns1.ispapi.net ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER][0] = ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER][1] = ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER0][0] = ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER0][1] = ns2.ispapi.net
PROPERTY[DOMAINNAMESERVER1][0] = ns1.ispapi.net
PROPERTY[DOMAINNAMESERVER1][1] = ns1.ispapi.net
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
PROPERTY[DOMAINREGISTRATIONEXPIRATIONDATE][0] = 2017-10-24 11:07:05
PROPERTY[DOMAINREGISTRATIONEXPIRATIONDATE][1] = 2017-10-24 23:59:59
PROPERTY[DOMAINRENEWALMODE][0] = renew
PROPERTY[DOMAINRENEWALMODE][1] = renew
PROPERTY[DOMAINRENEWALPERIOD][0] =
PROPERTY[DOMAINRENEWALPERIOD][1] =
PROPERTY[DOMAINREPOSITORY][0] = DONUTS-OTE-1API1
PROPERTY[DOMAINREPOSITORY][1] = CENTRALNIC-OTE-1API
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
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
PROPERTY[X-ACCEPT-WHOISTRUSTEE-TAC][0] =
PROPERTY[X-ACCEPT-WHOISTRUSTEE-TAC][1] =
PROPERTY[X-ACCEPT-WHOISTRUSTEELITE-TAC][0] =
PROPERTY[X-ACCEPT-WHOISTRUSTEELITE-TAC][1] =
PROPERTY[X-EXPIRED][0] =
PROPERTY[X-EXPIRED][1] =
PROPERTY[X-MOBI-ACCEPT-INSTANTMOBILIZER-TAC][0] =
PROPERTY[X-MOBI-ACCEPT-INSTANTMOBILIZER-TAC][1] =
PROPERTY[X-TRUSTEE][0] =
PROPERTY[X-TRUSTEE][1] =
EOF
```

----
## Notes
- USERDEPTH defines the depth of the returned list. `SELF` returns a list with only domains of the user itself. `SUBUSER` returns a list with domains of all direct subusers. `ALL` returns a list with domains of all subusers and all subusers below them.
- FIRST and LIMIT should be used to implement paging
