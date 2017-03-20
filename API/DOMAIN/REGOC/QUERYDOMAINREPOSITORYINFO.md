# QueryDomainRepositoryInfo

## DESCRIPTION
The command is used to list all available information for a certain domain repository.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainRepositoryInfo` | COMMAND
DOMAIN | 1 | Domain for which the repository information should be queried. This doesn't have to be a domain name in your posession | TEXT or NULL

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
ACCOUNTID | 1 | 1 | The respective ID of the account | INT
ADDONCLASS[0..N] | 0 | N | The respective addon classes for the domain repository| TEXT
ADDONDISPUTEEMAIL[0..N] | 0 | N | The respective dispute email addresses for the addons of the repository | TEXT
ADDONID[0..N] | 0 | N | The respective addon IDs for the domain repository | TEXT
ADDONNOTIFICATIONEMAIL[0..N] | 0 | N | The respective notification email addresses for the addons of the repository | TEXT
ADDONPOLICYOWNERCHANGE[0..N] | 0 | N | The respective policies for ownerchanges for the addons of the repository | TEXT
ADDONPROPERTYTYPE[0..N] | 0 | N | The respective property types for the addons of the repository | TEXT
ADDONPROPERTYVALUE[0..N] | 0 | N | The respective property values for the addons of the repository | TEXT
ADDONRENEWALGRACEPERIODSECONDS[0..N] | 0 | N | The respective renewal grace period seconds for the addons of the repository | TEXT
ADDONRENEWALPERIOD[0..N] | 0 | N | The respective renewal periods for the addons of the repository | TEXT
ADDONREPLACEPROPERTIES[0..N] | 0 | N | The respective properties that will be replaced by the addons of the repository | TEXT
CATEGORY[1..N] | 1 | N | The categories of the domain respository, e.g. `gTLD` for a repository that handles gTLDs | TEXT
DELETIONHOLDPERIOD | 1 | 1 | The deletion hold period for domains of the repository | TEXT
DELETIONRESTORABLEPERIOD | 1 | 1 | The deletion restorable period for domains of the repository | TEXT
HOSTIPADDRESSESTYPE | 1 | 1 | Type of host IP addresses | TEXT
HOSTMANAGEDAS | 1 | 1 | Type by which host objects will be manged, e.g. `HOST` | TEXT
LAUNCHPHASE[0..N] | 0 | N | Name of the respective launch phase | DATETIME
LAUNCHPHASEALLOCATION[0..N] | 0 | N | The allocation type of the respective launch phase, e.g. `AUCTION` | TEXT
LAUNCHPHASEEND[0..N] | 0 | N | End of the respective launch phase | DATETIME
LAUNCHPHASESTART[0..N] | 0 | N | Start of the respective launch phase | DATETIME
NAMESERVERMAX | 1 | 1 | Maximum amount of nameservers allowed | INT
NAMESERVERMIN | 1 | 1 | Minimum amount of nameservers required | INT
REGISTRAR | 1 | 1 | Name of registrar | TEXT
REGISTRYCHARSMAX | 0 | 1 | Maximum amount of characters for domains allowed by the registry | INT
REGISTRYCHARSMIN | 0 | 1 | Minimum amount of characters for domains required by the registry | INT
REGISTRYDISPUTEPOLICY | 0 | 1 | Link to registry's dispute policy | TEXT
REGISTRYDOMAINNAMECHARSET | 0 | 1 | Character set the registry allows for domains, e.g. `LETTERANDNUMBERS` | TEXT
REGISTRYDOMAINUPDATE | 0 | 1 | Indicates domain updates have to be done manually by the support team or if they can be processed automatically | TEXT
REGISTRYEXPLICITRENEWAL | 0 | 1 | Indicates if a registry allows explicit renewals or not, can be `YES` or `NO` | `YES` or `NO`
REGISTRYHANDLEUPDATE | 0 | 1 | Indicates if the registry supports contact handle updates or not | TEXT
REGISTRYIDNCAPABLE | 0 | 1 |  Indicates if a registry is capable of handling IDNs or not, can be `YES` or `NO` | `YES` or `NO`
REGISTRYIDNTAGTYPE | 0 | 1 | Type of IDN the registry uses | TEXT
REGISTRYNAMSERVERCHECKS | 0 | 1 | Description on the registry's nameserver check behavior | TEXT
REGISTRYNAMSERVERROOTUPDATE | 0 | 1 | Description on registry's nameserver sync intervals | TEXT
REGISTRYREGISTRATIONSYSTEM | 0 | 1 | Description on registry's registration system | TEXT
REGISTRYTRADEACKBY | 0 | 1 | Indicates by whom a trade is acknowledged by. Can be either `REGISTRY`, `CUSTOMER`, `BOTH` or `NONE` | TEXT
REGISTRYTRADENACKBY | 0 | 1 | Indicates by whom a trade is denied by. Can be either `REGISTRY`, `CUSTOMER`, `BOTH` or `NONE` | TEXT
REGISTRYTRADEREALTIME | 0 | 1 | Indicates if a ownerchange is performed in realtime at the registry, can be `YES` or `NO` | `YES` or `NO`
REGISTRYTRADETRANSFERINCLUDED | 0 | 1 | Indicates if a ownerchange can be performed together with a transfer, can be either `YES` or `NO` | `YES` or `NO`
REGISTRYTRANSFERACKBY | 0 | 1 | Indicates by whom a transfer is acknowledged. Can be `REGISTRAR`, `REGISTRY`, `CUSTOMER`, `BOTH`, `NONE` or `REGISTRANT` | TEXT
REGISTRYTRANSFERCLASS | 0 | 1 | The way a transfer is performed at the registry, can be `PUSH`, `PULL` or `OTHER` | `PUSH`, `PULL` or `OTHER`
REGISTRYTRANSFEREXPIREACTION | 0 | 1 | The registry transfer expiration action. Can be `ACK` or `NACK`  | `ACK` or `NACK`
REGISTRYTRANSFERLOCK | 0 | 1 | Indicates if the registry supports a transferlock or not, can be either `YES` or `NO` | `YES` or `NO`
REGISTRYTRANSFERNACKBY | 0 | 1 | Indicates by whom a transfer is declined. Can be `REGISTRAR`, `REGISTRY`, `CUSTOMER`, `BOTH`, `NONE` or `REGISTRANT` | `REGISTRAR`, `REGISTRY`, `CUSTOMER`, `BOTH`, `NONE` or `REGISTRANT`
REGISTRYTRANSFERPENDINGPERIOD | 0 | 1 | Indicates how long a transfer is pending at the registry | TEXT
REGISTRYTRANSFERREALTIME | 0 | 1 | Indicates if a transfer is processed in realtime at the registry or not, can be `YES` or `NO` | `YES` or `NO`
REGISTRYTRANSFERREQUIREAUTHCODE | 0 | 1 | Indicates if the registry requires an authcode to initiate a transfer, can be `YES` or `NO` | `YES` or `NO`
REGISTRYURL | 0 | 1 | URL to registry's website | TEXT
REGISTRYURLNAME | 0 | 1 | Name of registry's website | TEXT
REGISTRYWHOISSERVER | 0 | 1 | WHOIS server address | TEXT
REGISTRYWHOISUPDATE | 0 | 1 | Description on registry's WHOIS update behavior | TEXT
REPOSITORY | 1 | 1 | Name of the domain repository | TEXT
RESTOREPOLICY | 1 | 1 | Indicates the policy of restore. Can be `MANUAL`, `REALTIME`, `NONE`, `SPECIAL` or `NOREALTIME` | `MANUAL`, `REALTIME`, `NONE`, `SPECIAL` or `NOREALTIME`
X-PROXY | 1 | 1 | Deprecated: List of available Proxy addon keys | TEXT or NULL
ZONEADMINCONTACTSMAX | 1 | 1 | Maximum number of administrative contacts allowed by the registry for the zone | INT
ZONEADMINCONTACTSMIN | 1 | 1 | Minimum number of administrative contacts allowed by the registry for the zone | INT
ZONEBILLINGCONTACTSMAX | 1 | 1 | Maximum number of billing contacts allowed by the registry for the zone | INT
ZONEBILLINGCONTACTSMIN | 1 | 1 | Minimum number of billing contacts allowed by the registry for the zone | INT
ZONEPOLICYCONTACTORIGINCOUNTRY | 1 | 1 | Indicates which country of origin certain contacts have to have | TEXT or NULL
ZONEPOLICYCONTACTORIGINCOUNTRYREQUIREDFOR | 1| 1 | Indicates which contact have to be from a certain country of origin | TEXT or NULL
ZONEPOLICYDOMAINTRADEAPPROVECONFIRMATION | 1 | 1 | Indicates if the approval of a trade requires a confirmation | TEXT
ZONEPOLICYDOMAINTRADEREQUESTCONFIRMATION | 1 | 1 | Indicates if the request of a trade requires a confirmation | TEXT
ZONEPOLICYDOMAINTRANSFERAPPROVECONFIRMATION | 1 | 1 | Indicates if the approval of a transfer requires a confirmation | TEXT
ZONEPOLICYDOMAINTRANSFERREJECTCONFIRMATION | 1 | 1 | Indicates if the rejection of a transfer requires a confirmation | TEXT
ZONEPOLICYDOMAINTRANSFERREQUESTCONFIRMATION | 1 | 1 | Indicates if the request of a transfer requires a confirmation | TEXT
ZONEPOLICYREGISTRANTNAMECHANGEBY | 1 | 1 | Indicates how a registrant name change can be performed. Can be `UPDATE`, `REGISTRY`, `TRADE`, `ICANN-TRADE` or `NEWREG` | TEXT
ZONEREGISTRANTCONTACTSMAX | 1 | 1 | Maximum number of registrant contacts allowed by the registry for the zone | INT
ZONEREGISTRANTCONTACTSMIN | 1 | 1 | Minimum number of registrant contacts allowed by the registry for the zone | INT
ZONEREGISTRATIONGRACEPERIOD | 1 | 1 | Registration Grace Period of zone domains | TEXT
ZONEREGISTRATIONPERIODS | 1 | 1 | Registration periods supported for domains of the zone | TEXT
ZONERENEWALACCOUNTINGPERIOD | 1 | 1 | The renewal accounting period for domains of the zone | TEXT
ZONERENEWALFAILUREPERIOD | 1 | 1 | The renewal failure period for domains of the zone | TEXT
ZONERENEWALFINALIZATIONPERIOD | 1 | 1 |  The renewal finalization period for domains of the zone | TEXT
ZONERENEWALPAYMENTPERIOD | 1 | 1 | The renewal payment period for domains of the zone | TEXT
ZONERENEWALPERIODS | 1 | 1 | Renewal periods supported for the zone | TEXT
ZONESECDNSINTERFACE | 1 | 1 | Type of interface that is used for SECDNS, can be either `NONE` if SECDNS is not supported, `KEY` or `DS` | `NONE`, `KEY` or `DS`
ZONETECHCONTACTSMAX | 1 | 1 | Maximum number of technical contacts allowed by the registry for the zone | INT
ZONETECHCONTACTSMIN | 1 | 1 | Minimum number of technical contacts allowed by the registry for the zone | INT
ZONETRADEPERIODS | 1 | 1 | Trade periods supported for domains of the zone | TEXT
ZONETRANSFERPERIODS | 1 | 1 | Transfer periods supported for domains of the zone | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainRepositoryInfo
DOMAIN = example.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACCOUNTID][0] = 4535
PROPERTY[ADDONCLASS][0] = PROXY
PROPERTY[ADDONCLASS][1] = PROXY
PROPERTY[ADDONDISPUTEEMAIL][0] =
PROPERTY[ADDONDISPUTEEMAIL][1] =
PROPERTY[ADDONID][0] = WHOISTRUSTEE
PROPERTY[ADDONID][1] = WHOISTRUSTEELITE
PROPERTY[ADDONNOTIFICATIONEMAIL][0] =
PROPERTY[ADDONNOTIFICATIONEMAIL][1] =
PROPERTY[ADDONPOLICYOWNERCHANGE][0] = IGNORE
PROPERTY[ADDONPOLICYOWNERCHANGE][1] = IGNORE
PROPERTY[ADDONPROPERTYTYPE][0] = X-ACCEPT-WHOISTRUSTEE-TAC
PROPERTY[ADDONPROPERTYTYPE][1] = X-ACCEPT-WHOISTRUSTEELITE-TAC
PROPERTY[ADDONPROPERTYVALUE][0] = 1
PROPERTY[ADDONPROPERTYVALUE][1] = 1
PROPERTY[ADDONRENEWALGRACEPERIODSECONDS][0] = 0
PROPERTY[ADDONRENEWALGRACEPERIODSECONDS][1] = 0
PROPERTY[ADDONRENEWALPERIOD][0] = 1M
PROPERTY[ADDONRENEWALPERIOD][1] = 1M
PROPERTY[ADDONREPLACEPROPERTIES][0] =
PROPERTY[ADDONREPLACEPROPERTIES][1] =
PROPERTY[CATEGORY][0] = ICANN
PROPERTY[CATEGORY][1] = gTLD
PROPERTY[DELETIONHOLDPERIOD][0] = 5d
PROPERTY[DELETIONRESTORABLEPERIOD][0] = 30d
PROPERTY[HOSTIPADDRESSESTYPE][0] = ipv6
PROPERTY[HOSTMANAGEDAS][0] = OBJECT
PROPERTY[NAMESERVERMAX][0] = 13
PROPERTY[NAMESERVERMIN][0] = 0
PROPERTY[REGISTRAR][0] = 1api GmbH
PROPERTY[REGISTRYCHARSMAX][0] = 63
PROPERTY[REGISTRYCHARSMIN][0] = 3
PROPERTY[REGISTRYDISPUTEPOLICY][0] = http://www.icann.org/udrp/udrp-rules-24oct99.htm
PROPERTY[REGISTRYDOMAINNAMECHARSET][0] = LETTERANDNUMBERS
PROPERTY[REGISTRYEXPLICITRENEWAL][0] = YES
PROPERTY[REGISTRYHANDLEUPDATE][0] = Supported
PROPERTY[REGISTRYIDNCAPABLE][0] = Yes
PROPERTY[REGISTRYNAMESERVERCHECKS][0] = NO
PROPERTY[REGISTRYNAMESERVERROOTUPDATE][0] = Real-Time
PROPERTY[REGISTRYREGISTRATIONSYSTEM][0] = Real-Time
PROPERTY[REGISTRYTRANSFERACKBY][0] = REGISTRAR
PROPERTY[REGISTRYTRANSFERCLASS][0] = PULL
PROPERTY[REGISTRYTRANSFEREXPIREACTION][0] = ACK
PROPERTY[REGISTRYTRANSFERLOCK][0] = YES
PROPERTY[REGISTRYTRANSFERNACKBY][0] = REGISTRAR
PROPERTY[REGISTRYTRANSFERPENDINGPERIOD][0] = 5d
PROPERTY[REGISTRYTRANSFERREALTIME][0] = NO
PROPERTY[REGISTRYTRANSFERREQUIREAUTHCODE][0] = YES
PROPERTY[REGISTRYURL][0] = http://www.verisign.com/information-services/index.html
PROPERTY[REGISTRYURLNAME][0] = VeriSign
PROPERTY[REGISTRYWHOISSERVER][0] = -
PROPERTY[REGISTRYWHOISUPDATE][0] = Real-Time
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[RESTOREPOLICY][0] = REALTIME
PROPERTY[X-PROXY][0] = X-ACCEPT-WHOISTRUSTEE-TAC X-ACCEPT-WHOISTRUSTEELITE-TAC
PROPERTY[ZONEADMINCONTACTSMAX][0] = 1
PROPERTY[ZONEADMINCONTACTSMIN][0] = 1
PROPERTY[ZONEBILLINGCONTACTSMAX][0] = 2
PROPERTY[ZONEBILLINGCONTACTSMIN][0] = 0
PROPERTY[ZONEPOLICYCONTACTORIGINCOUNTRY][0] =
PROPERTY[ZONEPOLICYCONTACTORIGINCOUNTRYREQUIREDFOR][0] = NONE
PROPERTY[ZONEPOLICYDOMAINTRADEAPPROVECONFIRMATION][0] =
PROPERTY[ZONEPOLICYDOMAINTRADEREQUESTCONFIRMATION][0] =
PROPERTY[ZONEPOLICYDOMAINTRANSFERAPPROVECONFIRMATION][0] = EMAIL
PROPERTY[ZONEPOLICYDOMAINTRANSFERREJECTCONFIRMATION][0] = ICANN-FOA-REJECT
PROPERTY[ZONEPOLICYDOMAINTRANSFERREQUESTCONFIRMATION][0] = ICANN-FOA-REQUEST
PROPERTY[ZONEPOLICYREGISTRANTNAMECHANGEBY][0] = ICANN-TRADE
PROPERTY[ZONEREGISTRANTCONTACTSMAX][0] = 1
PROPERTY[ZONEREGISTRANTCONTACTSMIN][0] = 1
PROPERTY[ZONEREGISTRATIONGRACEPERIOD][0] = 0
PROPERTY[ZONEREGISTRATIONPERIOD][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y,10Y
PROPERTY[ZONEREGISTRATIONPERIODS][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y,10Y
PROPERTY[ZONERENEWALACCOUNTINGPERIOD][0] = -5d
PROPERTY[ZONERENEWALFAILUREPERIOD][0] = 44d
PROPERTY[ZONERENEWALFINALIZATIONPERIOD][0] = 1d
PROPERTY[ZONERENEWALPAYMENTPERIOD][0] = -61d
PROPERTY[ZONERENEWALPERIODS][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y
PROPERTY[ZONESECDNSINTERFACE][0] = DS
PROPERTY[ZONETECHCONTACTSMAX][0] = 2
PROPERTY[ZONETECHCONTACTSMIN][0] = 1
PROPERTY[ZONETRADEPERIODS][0] =
PROPERTY[ZONETRANSFERPERIODS][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y,10Y
EOF
```

----
