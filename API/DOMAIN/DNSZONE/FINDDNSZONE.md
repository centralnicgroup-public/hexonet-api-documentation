# FindDNSZone

## DESCRIPTION
Searches for a certain DNS zone by nameserver name or IP address.

## AVAILABILITY
Always, if zone is assigned to your user account.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `FindDNSZone` | COMMAND
RTYPE | 1 | Type of DNS record, can be NS, A, MX, ... | NULL or TEXT
RDATA | 1 | Name of one of the nameservers or IP address | NULL or TEXT

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
530 | Authentication failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 0 | 1 | Number of resource records returned | INT
TOTAL | 0 | 1 | Total number of resource records found | INT
CLASS | 0 | N | Class of resource record | TEXT
DATA | 0 | N | Data part of the matching resource record | TEXT
DNSZONE | 0 | N | Zone in which the record has been found | TEXT
DOMAIN | 0 | N | Domain part of the matching resource record | TEXT
TTL | 0 | N | TTL part of the matching resource record | INT
TYPE | 0 | N | Type of the resource record | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = FindDNSZone
RDATA = ns2.hexonet.net.
RTYPE = NS
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[COUNT][0] = 4
PROPERTY[TOTAL][0] = 4
PROPERTY[CLASS][0] = IN
PROPERTY[CLASS][1] = IN
PROPERTY[CLASS][2] = IN
PROPERTY[CLASS][3] = IN
PROPERTY[DATA][0] = ns2.hexonet.net.
PROPERTY[DATA][1] = ns2.hexonet.net.
PROPERTY[DATA][2] = ns2.hexonet.net.
PROPERTY[DATA][3] = ns2.hexonet.net.
PROPERTY[DNSZONE][0] = abc123xyz.biz.
PROPERTY[DNSZONE][1] = xyz123abc.de.
PROPERTY[DNSZONE][2] = abc123xyz.com.
PROPERTY[DNSZONE][3] = xyz123abc.it.
PROPERTY[DOMAIN][0] = abc123xyz.biz.
PROPERTY[DOMAIN][1] = xyz123abc.de.
PROPERTY[DOMAIN][2] = abc123xyz.com.
PROPERTY[DOMAIN][3] = xyz123abc.it.
PROPERTY[TTL][0] = 3600
PROPERTY[TTL][1] = 3600
PROPERTY[TTL][2] = 3600
PROPERTY[TTL][3] = 86400
PROPERTY[TYPE][0] = NS
PROPERTY[TYPE][1] = NS
PROPERTY[TYPE][2] = NS
PROPERTY[TYPE][3] = NS
EOF
```

----
