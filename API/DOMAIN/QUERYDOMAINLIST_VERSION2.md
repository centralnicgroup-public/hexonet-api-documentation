# QueryDomainList Version 2

## DESCRIPTION
Query a list of domains and other domain related objects such as domain applications and transfers.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainList` | COMMAND
VERSION | 1 | Indicates the version of the command. To access this version 2 of QueryDomainsList, `2` must be use used as value | INT
WIDE | 0 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
NOTOTAL | 0 | Set to `0` to suppress the return of the TOTAL response property. This will impore response time. If set to `1` the TOTAL response property will be returned | `0` or `1`
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`OBJECTID`, `OBJECTIDDESC`, `DESCRIPTION`, `DESCRIPTIONDESC`, `CREATEDDATE`, `CREATEDDATEDESC`, `UPDATEDDATE`, `UPDATEDDATEDESC`, `EXPIRATIONDATE`, `EXPIRATIONDATEDESC`, `FINALIZATIONDATE`, `FINALIZATIONDATEDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
PROPERTIES | 0 | Additional properties to be returned can be specified here. Currently supported values are:<br>`TRANSFER`: if used, the response will contain the transfer related propeties TRANSFER-CREATEDDATE, TRANSFER-DIRECTION, TRANSFER-NEWREGISTRAR, TRANSFER-OLDREGISTRAR and TRANSFER-STATUS<br>`PRICE`: if used, the response will contain the properties CURRENCY, RENEWALGROSSPRICE, RENEWALPRICE and VAT | TEXT or NULL
DESCRIPTION | 0 | Only show objects with an description that matches the pattern specified here. | PATTERN or TEXT
DOMAIN | 0 | Only show objects where the domain name matches the pattern specified here. | PATTERN or TEXT
DOMAIN[0..N] | 0 | Only show domains stated here | TEXT
DOMAINREGEX | 0 | Only show objects where the domain name matches the regular expression specified here | REGEX or NULL
DOMAINREGEXNOT | 0 | Only show objects where the domain name does not matche the regular expression specified here | REGEX or NULL
EXTENDED | 0 | If set to `1` an extended domain list will get returned | `0` or `1`
OBJECTID | 0 | Only show objects with an ID that matches the pattern specified here | PATTERN or TEXT
OBJECTCLASS | 0 | Only show objects with an object class that matches the pattern specified here | TEXT or NULL
OBJECTCLASSREGEX | 0 | Only show objects with an object class that matches the regular expression specified here | REGEX or NULL
OBJECTCLASSREGEXNOT | 0 | Only show objects with an object class that does not match the regular expression specified here | REGEX or NULL
SUBCLASS | 0 |  Only show objects with an object subclass that matches the pattern specified here | TEXT or NULL
SUBCLASSREGEX | 0 | Only show objects with an object subclass that matches the regular expression specified here | REGEX or NULL
SUBCLASSREGEXNOT | 0 | Only show objects with an object subclass that does not match the regular expression specified here | REGEX or NULL
STATUS | 0 | Only show domains with a status that matches the pattern specified here | PATTERN
STATUSREGEX | 0 | Only show domains with a status that matches the regular expression specified here | REGEX or NULL
STATUSREGEXNOT | 0 | Only show domains with a status that does not match the regular expression specified here | REGEX or NULL
MINCREATEDDATE | 0 | Minimal creation date of returned objects | NULL or TEXT
MAXCREATEDDATE | 0 | Maximal creation date of returned objects | NULL or TEXT
MINUPDATEDDATE | 0 | Minimal updated date of returned objects | NULL or TEXT
MAXUPDATEDDATE | 0 | Maximal updated date of returned objects | NULL or TEXT
MINEXPIRATIONDATE | 0 | Minimal expiration date of returned objects | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Maximal expiration date of returned objects | NULL or TEXT
MINPAIDUNTILDATE | 0 | Minimal paid until date of returned objects | NULL or TEXT
MAXPAIDUNTILDATE | 0 | Maximal paid until date of returned objects | NULL or TEXT
RENEWALMODE | 0 | Show only objects which are set to the renewal mode specified here.<br>Can be `AUTOEXPIRE`, `AUTODELETE` or `AUTORENEW` | NULL or TEXT
REPOSITORY | 0 | Only show domains which belong to a repository that matches the pattern specified here | NULL or TEXT
USER | 0 | Only show domains which belong to a user that matches the pattern specified here | PATTERN or TEXT
SUBUSER | 0 | Sub user | TEXT or NULL
ADDON-TRUSTEE | 0 | Only show domain objects that that have a local presence service activated that matches the pattern specified here. Set to `0` to only show objects that do not have any local presence service activated | TEXT or NULL
ADDON-PROXY | 0 | Only show domain objects that that have a privacy service activated that matches the pattern specified here. Set to `0` to only show objects that do not have any privacy service activated | TEXT or NULL
OWNERCONTACT | 0 | Owner contact | PATTERN
ADMINCONTACT | 0 | Admin contact | PATTERN
TECHCONTACT | 0 | Tech contact | PATTERN
BILLINGCONTACT | 0 | Billing contact | PATTERN
CONTACT | 0 | Any of the domain contacts | PATTERN
TRANSFER-DIRECTION | 0 | Transfer direction | `IN`, `OUT` or `TRADE`

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
506	| Invalid option value
530 | Authentication failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found. | INT
ACCOUNTINGDATE[0..N] | 0 | N | Accounting Date of the respective domain name | DATE
ADMINCONTACT[0..N] | 0 | N | The Administrative Contact/s. If more than one, separated by spaces | TEXT
AUTH[0..N] | 0 | N | Authorization code of the respective domain name | TEXT
BILLINGCONTACT[0..N] | 0 | N | The Billing Contact/s. If more than one, separated by spaces | TEXT
CLAIMKEY[0..N] | 0 | N | The claim key of Domain Applications that have one | TEXT
CREATEDDATE[0..N] | 0 | N | Creation date of the object | DATE
CURRENCY[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: The currency for RENEWALGROSSPRICE and RENEWALPRICE | TEXT
DESCRIPTION[0..N] | 0 | N | The U-label of the domain associated with the object | DATE
EXPIRATIONDATE[0..N] | 0 | N | Expiration date of the respective domain name | DATE
FAILUREDATE[0..N] | 0 | N | Failure date of the respective domain name | DATE
FINALIZATIONDATE[0..N] | 0 | N | Finalization date of the respective domain name | DATE
INTERNALNAMESERVER[0..N] | 0 | N | A list of nameservers that are managed internally for the domain name, separated by spaces | TEXT
INVALIDPARAMETER[0..N] | 0 | N | List of invalid parameters of a domain application, separated by spaces. This property only relates to DomainApplications. If this property has a value the respective DomainApplication is INCOMPLETE | TEXT
MISSINGPARAMETER[0..N] | 0 | N | List of missing parameters of a domain application, separated by spaces. This property only relates to DomainApplications. If this property has a value the respective DomainApplication is INCOMPLETE | TEXT
NAMESERVER[0..N] | 0 | N | Shows a list of the nameservers of the domain separated by spaces | TEXT
NEXTACTION[0..N] | 0 | N | Defines the next action to perform on a domain. It can be:<br>`pay`: Only applies for RENEWALMODE: AUTORENEW. Before the ACCOUNTINGDATE, a payment from the domain's respective user account will be charged. If payment fails, the NEXTACTION remains "pay" for one more day. A second failed charge attempt changes NEXTACTION to `expireunpaid`.<br>`finalize`: Only applies for RENEWALMODE: AUTORENEW. After the ACCOUNTINGDATE and after a successful payment, the NEXTACTION is `finalize` (execute domain renewal) on the FINALIZATIONDATE. Please remember that on or after the FINALIZATIONDATE, a domain renewal cannot be stopped and no refunds are offered.<br>`expire`: Only applies for RENEWALMODE: AUTOEXPIRE. The NextAction is to transfer the domain to the respective registry on the FailureDate. Please note that this only applies to a handful of TLDs (e.g. .DE, .AT).<br>`expireunpaid`: Only applies for RENEWALMODE: AUTORENEW. If payment can not be charged on the ACCOUNTINGDATE, this action applies. As a result, on the FAILUREDATE for the domain, the domain is either deleted or transferred to the respective registry.<br>`delete`: This action applies only if RENEWALMODE: AUTODELETE. The domain will be deleted on its FAILUREDATE. | TEXT
NEXTACTIONDATE[0..N] | 0 | N | The date the NEXTACTION will occur | DATE
OBJECTCLASS[0..N] | 0 | N | The class of the object. Can be `DOMAIN`, `DOMAINAPPLICATION` or `DOMAINTRANSFER` | TEXT
ONBJECTID[0..N] | 0 | N | The ID of the object. If the object is a domain, OBJECTID corresponds to the A-label of the domain | TEXT
OWNERCONTACT[0..N] | 0 | N | The Registrant/Owner Contact/s. If more than one, separated by spaces | TEXT
PAIDUNTILDATE[0..N] | 0 | N | Paid until date of the respective domain name| DATE
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
PREPAIDPERIOD[0..N] | 0 | N | The prepaid period of the respective domain name | PERIOD
RENEWALGROSSPRICE[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: Gross price of the upcoming renewal | DECIMAL
RENEWALMODE[0..N] | 0 | N | Renewal mode of the respective object.<br> Can be `AUTODELETE`, `AUTORENEW` or `AUTOEXPIRE` | `AUTODELETE`, `AUTORENEW` or `AUTOEXPIRE`
RENEWALPERIOD[0..N] | 0 | N | The period the domain will get renewed in AUTORENEW mode | PERIOD
REPOSITORY[0..N] | 0 | N | Domain repository the respective objects belongs to | TEXT
RENEWALPRICE[0..N] | 0 | N | Only displayed if PROPERTIES is set to `RENEWALPRICE`: Price of the upcoming renewal not including taxes | DECIMAL
ROID[0..N] | 0 | N | The Registry Domain ID | TEXT
STATUS[0..N] | 0 | N | Status of the respective object | TEXT
SUBCLASS[0..N] | 0 | N | The subclass of the respective object | TEXT
TECHCONTACT[0..N] | 0 | N | The Technical Contact/s. If more than one, separated by spaces | TEXT
TRANSFER-CREATEDDATE[0..N] | 0 | N | Creation date of the current pending transfer | DATETIME
TRANSFER-DIRECTION[0..N] | 0 | N | The direction of the transfer. It can be:<br>`IN`: A transfer to the registrar<br>`OUT`: A transfer to an external registrar (foreign transfer)<br>`TRADE`: A domain trade | `IN`, `OUT` or `TRADE`
TRANSFER-NEWREGISTRAR[0..N] | 0 | N | Gaining Registrar | TEXT
TRANSFER-OLDREGISTRAR[0..N] | 0 | N | Loosing Registrar | TEXT
TRANSFER-STATUS[0..N] | 0 | N | Current status of the transfer | TEXT
TRANSFERDATE[0..N] | 0 | N | The date of last successful incoming transfer | DATE
TRANSFERLOCK[0..N] | 0 | N | Shows if a transferlock is active or not  | `0`, `1` or NULL
UPDATEDDATE[0..N] | 0 | N | Last modification date of the domain object | DATE
USER[0..N] | 0 | N | The user ID that the object belongs to | TEXT
VAT[0..N] | 0 | N | Value Added Tax for RENEWALGROSSPRICE | DIGIT
X-PRICE-CLASS[0..N] | 0 | N | The price class that a domain application will belong to once it becomes a domain | TEXT
ADDON-PROXY[0..N] | 0 | N | Privacy Service that is activated for the domain name. Will be `0` if no Privacy Service is activated for the domain name. | `0`, `WHOISTRUSTEE`, `WHOISTRUSTEELITE` or NULL
ADDON-TRUSTEE[0..N] | 0 | N | Local Presence Service that is activated for the domain name. Will be `0` if no Local Presence Service is activated for the domain name. | `0`, `LAWFIRNAME` or NULL


----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainList
LIMIT = 1
TOTAL = 1
PROPERTIES = PRICE
VERSION = 2
WIDE = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 0
PROPERTY[COUNT][0] = 1
PROPERTY[TOTAL][0] = 1
PROPERTY[LIMIT][0] = 1
PROPERTY[ACCOUNTINGDATE][0] = 2017-07-23 11:00:06
PROPERTY[ADMINCONTACT][0] = P-BAH153975
PROPERTY[AUTH][0] = ZqIYcu/Y3N6F
PROPERTY[BILLINGCONTACT][0] = P-BAH153975
PROPERTY[CLAIMKEY][0] =
PROPERTY[CREATEDDATE][0] = 2016-07-28 11:00:06
PROPERTY[CURRENCY][0] = EUR
PROPERTY[DESCRIPTION][0] = 0-60human.com
PROPERTY[EXPIRATIONDATE][0] = 2017-07-28 11:00:06
PROPERTY[FAILUREDATE][0] = 2017-09-10 11:00:06
PROPERTY[FINALIZATIONDATE][0] = 2017-07-29 11:00:06
PROPERTY[INTERNALNAMESERVER][0] = ns3.ispapi.net ns1.ispapi.net ns2.ispapi.net
PROPERTY[INVALIDPARAMETER][0] =
PROPERTY[MISSINGPARAMETER][0] =
PROPERTY[NAMESERVER][0] = ns3.ispapi.net ns2.ispapi.net ns1.ispapi.net
PROPERTY[NEXTACTION][0] = pay
PROPERTY[NEXTACTIONDATE][0] = 2017-07-23 11:00:06
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTID][0] = 0-60human.com
PROPERTY[OWNERCONTACT][0] = P-BAH153975
PROPERTY[PAIDUNTILDATE][0] = 2017-07-28 11:00:06
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PREPAIDPERIOD][0] = 0
PROPERTY[RENEWALGROSSPRICE][0] = 0.00
PROPERTY[RENEWALMODE][0] = renew
PROPERTY[RENEWALPERIOD][0] = 1Y
PROPERTY[RENEWALPRICE][0] = 0.00
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[ROID][0] =
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[SUBCLASS][0] = COM
PROPERTY[TECHCONTACT][0] = P-BAH153975
PROPERTY[TRANSFERDATE][0] =
PROPERTY[TRANSFERLOCK][0] = 0
PROPERTY[UPDATEDDATE][0] = 2016-07-28 11:00:06
PROPERTY[USER][0] = test.user
PROPERTY[VAT][0] = 19.00
PROPERTY[X-ACCEPT-WHOISTRUSTEE-TAC][0] = 0
PROPERTY[X-ACCEPT-WHOISTRUSTEELITE-TAC][0] = 0
EOF
```

----
## Notes
- USERDEPTH defines the depth of the returned list. `SELF` returns a list with only domains of the user itself. `SUBUSER` returns a list with domains of all direct subusers. `ALL` returns a list with domains of all subusers and all subusers below them.
- FIRST and LIMIT should be used to implement paging
