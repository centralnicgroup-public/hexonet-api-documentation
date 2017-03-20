# StatusDNSZone

## DESCRIPTION
Queries the status of an existing DNS zone.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDNSZone` | COMMAND
DNSZONE | 1 | Name of the zone to be queried | TEXT
EXTENDED | 0 | Switch to return EXTENDED properties, for URL / EMAIL forwardings | `0` or `1`

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
531 | Authorization failed
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDDATE | 1 | 1 | Created date of the dnszone, e.g. 2003-12-23 18:11:48 | DATE
DNSSEC-MODE | 1 | 1 | Returns if DNSSEC is enabled or not | TEXT
PEERUSER | 1 | 1 | Subuserchain of the zone | TEXT
RRSTOTAL | 1 | 1 | Total number of resource records contained in the zone | INT
SOAEXPIRE | 1 | 1 | EXPIRE of the SOA record | INT
SOAMINTTL | 1 | 1 | MINTTL of the SOA record | INT
SOAMNAME | 1 | 1 | MNAME of the SOA record | TEXT
SOAREFRESH | 1 | 1 | REFRESH of the SOA record | INT
SOARETRY | 1 | 1 | RETRY of the SOA record | INT
SOARNAME | 1 | 1 | RNAME of the SOA record | TEXT
SOASERIAL | 1 | 1 | Value that indicates the "actuality" of the SOA-Record to other nameservers. The soaserial must be increased (or at least incremented) on every zoneupdate | INT
SOATTL | 1 | 1 | TTL of the SOA record | INT
STATUS | 1 | 1 | STATUS of the DNS zone, e.g. ACTIVE, INACTIVE | TEXT
UPDATEDDATE | 1 | 1 | Last updated date of the dnszone, e.g. 2003-12-23 18:11:48 | DATE
WWWTARGETDATA | 1 | 1 | Destination of the www subdomain inside the zone | TEXT
WWWTARGETTYPE | 1 | 1 | Type of the www subdomain inside the zone | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDNSZone
DNSZONE = domain.com.
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2009-02-10 09:46:03
PROPERTY[DNSSEC-MODE][0] = DISABLED
PROPERTY[PEERUSER][0] = ispproxy.net isp.zeitguys
PROPERTY[RRSTOTAL][0] = 7
PROPERTY[SOAEXPIRE][0] = 3600000
PROPERTY[SOAMINTTL][0] = 172800
PROPERTY[SOAMNAME][0] = ns1.domain.com.
PROPERTY[SOAREFRESH][0] = 86400
PROPERTY[SOARETRY][0] = 7200
PROPERTY[SOARNAME][0] = hostmaster.domain.com.
PROPERTY[SOASERIAL][0] = 2009021000
PROPERTY[SOATTL][0] = 3600
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[UPDATEDDATE][0] = 2009-02-10 09:46:03
PROPERTY[WWWTARGETDATA][0] = domain.com.
PROPERTY[WWWTARGETTYPE][0] = CNAME
EOF
```

----
