# QueryDomainOptions

## DESCRIPTION
The command is used to list all supported options available for a domain.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainOptions` | COMMAND
DOMAIN[0..N] | 0 | Domain Name | DOMAIN
REPOSITORY[0..N] | 0 | Domain Repository | TEXT or NULL
PROPERTIES | 0 | Display additional information; can be `LAUNCHPHASES` | TEXT

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
HOSTIPADDRESSESTYPE[0..N] | 0 | N | Host IP address support; can be `ipv4` (only IPv4 support) or `ipv6` (IPv4 and IPv6 support) | TEXT
HOSTMANAGEDAS[0..N] | 0 | N | Type of host; can be `ATTRIBUTE` or `OBJECT` | TEXT
LAUNCHPHASES[0..N] | 0 | N | Available launch phases | TEXT
LAUNCHPHASESALLOCATIONTYPE[0..N] | 0 | N | Allocation type for each launch phase; can be `AUCTION` or `FCFS` (first-come, first-served) | TEXT
LAUNCHPHASESAPPLICATIONDATE[0..N] | 0 | N | Date from which on one can start applying for each launch phase | TEXT
LAUNCHPHASESCLOSEDATE[0..N] | 0 | N | End date for each launch phase | TEXT
LAUNCHPHASESSTARTDATE[0..N] | 0 | N | Start date for each launch phase | TEXT
NAMESERVERMAX[0..N] | 0 | N | Maximum number of nameservers | INT
NAMESERVERMIN[0..N] | 0 | N | Minimum number of nameservers | INT
REPOSITORY[0..N] | 0 | N | Domain repository | TEXT
X-INSTANTMOBILIZER[0..N] | 0 | N | Instant Mobilizer service; empty if not supported | TEXT
X-PROXY[0..N] | 0 | N | WhoisTrustee service; empty if not supported | TEXT
X-TRUSTEE[0..N] | 0 | N | Trustee service; empty if not supported | TEXT
ZONEADMINCONTACTSMAX[0..N] | 0 | N | Maximum number of administrative contacts | INT
ZONEADMINCONTACTSMIN[0..N] | 0 | N | Minimum number of administrative contacts | INT
ZONEBILLINGCONTACTSMAX[0..N] | 0 | N | Maximum number of billing contacts | INT
ZONEBILLINGCONTACTSMIN[0..N] | 0 | N | Minimum number of billing contacts | INT
ZONEPOLICYDOMAINTRADEAPPROVECONFIRMATION[0..N] | 0 | N | Policy or email template name in case a special trade approval procedure is in place (e.g. `FAX` or `ICANN-TRADE-CONFIRMATION-OLD-REGISTRANT`)  | TEXT
ZONEPOLICYDOMAINTRADEREQUESTCONFIRMATION[0..N] | 0 | N | Policy in case a special procedure to initiate a trade is in place (e.g. `EMAIL` or `MAIL`) | TEXT
ZONEPOLICYDOMAINTRANSFERAPPROVECONFIRMATION[0..N] | 0 | N | Policy in case a special procedure to approve a transfer is in place (e.g. `EMAIL`, `FAX` or `REALTIME`) | TEXT
ZONEPOLICYDOMAINTRANSFERREJECTCONFIRMATION[0..N] | 0 | N | Email template in case a special procedure to reject outgoing transfers is in place (e.g. `ICANN-FOA-REJECT`) | TEXT
ZONEPOLICYDOMAINTRANSFERREQUESTCONFIRMATION[0..N] | 0 | N | Email template in case a special procedure to initiate a transfer is in place (e.g. `ICANN-FOA-REQUEST`) | TEXT
ZONEPOLICYREGISTRANTNAMECHANGEBY[0..N] | 0 | N | Method used in order to change the registrant | TEXT
ZONEREGISTRANTCONTACTSMAX[0..N] | 0 | N | Maximum number of registrant contacts | INT
ZONEREGISTRANTCONTACTSMIN[0..N] | 0 | N | Minimum number of registrant contacts | INT
ZONEREGISTRATIONPERIODS[0..N] | 0 | N | Available registration periods | TEXT
ZONERENEWALPERIODS[0..N] | 0 | N | Available renewal periods | TEXT
ZONETECHCONTACTSMAX[0..N] | 0 | N | Maximum number of technical contacts | INT
ZONETECHCONTACTSMIN[0..N] | 0 | N | Minimum number of technical contacts | INT
ZONETRANSFERPERIODS[0..N] | 0 | N | Available transfer periods | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainOptions
DOMAIN0 = domain.shop
PROPERTIES = LAUNCHPHASES
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[HOSTIPADDRESSESTYPE][0] = ipv6
PROPERTY[HOSTMANAGEDAS][0] = OBJECT
PROPERTY[LAUNCHPHASES][0] = SHOP_SUNRISE,SHOP_EARLYACCESS1,SHOP_EARLYACCESS2,SHOP_EARLYACCESS3,SHOP_EARLYACCESS4,SHOP_EARLYACCESS5,SHOP_EARLYACCESS6,SHOP_EARLYACCESS7,SHOP_GOLIVE
PROPERTY[LAUNCHPHASESALLOCATIONTYPE][0] = AUCTION,FCFS,FCFS,FCFS,FCFS,FCFS,FCFS,FCFS,FCFS
PROPERTY[LAUNCHPHASESAPPLICATIONDATE][0] = 2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00,2016-06-30 15:00:00
PROPERTY[LAUNCHPHASESCLOSEDATE][0] = 2016-08-29 23:59:00,2016-09-03 14:59:00,2016-09-06 14:59:00,2016-09-10 14:59:00,2016-09-14 14:59:00,2016-09-18 14:59:00,2016-09-22 14:59:00,2016-09-26 14:59:00,
PROPERTY[LAUNCHPHASESSTARTDATE][0] = 2016-06-30 15:00:00,2016-09-01 15:00:00,2016-09-03 15:00:00,2016-09-06 15:00:00,2016-09-10 15:00:00,2016-09-14 15:00:00,2016-09-18 15:00:00,2016-09-22 15:00:00,2016-09-18 15:00:00
PROPERTY[NAMESERVERMAX][0] = 13
PROPERTY[NAMESERVERMIN][0] = 0
PROPERTY[REPOSITORY][0] = SHOP-OTE-1API1
PROPERTY[X-INSTANTMOBILIZER][0] =
PROPERTY[X-PROXY][0] =
PROPERTY[X-TRUSTEE][0] =
PROPERTY[ZONEADMINCONTACTSMAX][0] = 1
PROPERTY[ZONEADMINCONTACTSMIN][0] = 1
PROPERTY[ZONEBILLINGCONTACTSMAX][0] = 1
PROPERTY[ZONEBILLINGCONTACTSMIN][0] = 1
PROPERTY[ZONEPOLICYREGISTRANTNAMECHANGEBY][0] = ICANN-TRADE
PROPERTY[ZONEREGISTRANTCONTACTSMAX][0] = 1
PROPERTY[ZONEREGISTRANTCONTACTSMIN][0] = 1
PROPERTY[ZONEREGISTRATIONPERIODS][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y,10Y
PROPERTY[ZONERENEWALPERIODS][0] = 1Y,2Y,3Y,4Y,5Y,6Y,7Y,8Y,9Y
PROPERTY[ZONETECHCONTACTSMAX][0] = 1
PROPERTY[ZONETECHCONTACTSMIN][0] = 1
PROPERTY[ZONETRANSFERPERIODS][0] = 1Y
EOF
```

----
