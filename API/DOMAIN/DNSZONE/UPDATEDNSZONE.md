# UpdateDNSZone

## DESCRIPTION
With this command you can add, overwrite or remove records in a zone.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateDNSZone` | COMMAND
DNSZONE | 1 | Name of the zone that shall be modified. | TEXT
SOATTL | 0 | Time to live of the whole zone | INT
SOAMNAME | 0 | Master nameserver of the zone | TEXT
SOARNAME | 0 | Responsible person (mailadress with "@" substituted by ".") for the zone | TEXT
SOASERIAL | 0 | Value that indicates the "actuality" of the SOA-Record to other nameservers. The soaserial must be increased (or at least incremented) on every zoneupdate | INT
SOAREFRESH | 0 | See the accordant RFC (listed below) for details | INT
SOARETRY | 0 | See the accordant RFC (listed below) for details | INT
SOAEXPIRE | 0 | See the accordant RFC (listed below) for details | INT
SOAMINTTL | 0 | See the accordant RFC (listed below) for details | INT
INCSERIAL | 0 | Increases the zone serial by 1 if submitted | INT
RESOLVETTLCONFLICTS | 0 | Automatically resolve TTL conflicts if possible | `0` or `1`
RR[0..N] | 0 | When using "rr" as parameter in UpdateDNSZone, all existing records (besides the SOA record of course) will get deleted and replaced by the new records, defined by rr0, rr1, ... | LONGTEXT
ADDRR[0..N] | 0 | Add one or more new DNS records to the zone. The existing records are not touched by this parameter. The new records are appended to the existing ones. | LONGTEXT
DELRR[0..N] | 0 | Delete one or more DNS records | LONGTEXT
STATUS | 0 | Change status of the zone | `ACTIVE`, `INACTIVE`, `HOLD` or NULL
X-SMTP-MX | 0 | Set special MX record in EXTENDED mode | TEXT or NULL
X-HTTP-A | 0 | Set special destination IP address in EXTENDED mode | TEXT or NULL
EXTENDED | 0 | Switch to EXTENDED mode to manage forwardings | `0` or `1`
ZONEMODE | 0 | Set zonemode to MASTER or SLAVE | `MASTER` or `SLAVE`
SLAVEMASTER | 0 | Set the master nameserver in case the zonemode is SLAVE | TEXT or NULL
DNSSEC-MODE | 0 | DNSSEC mode, `AUTO` or `DISABLED` | `DISABLED`, `AUTO`

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
506 | Invalid option value; Syntax error in parameter: x
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value; duplicate record [domain.com. 3600 IN A 192.168.0.1]
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
SOASERIAL | 1 | 1 | The SERIAL of the DNS zone. If INCSERIAL=1 is provided this is the new SERIAL. | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = UpdateDNSZone
ADDRR0 = domain.com. 3600 IN A 192.168.0.2
DELRR0 = @ 3600 IN A 192.168.0.1
DNSZONE = domain.com.
RR0 = @ IN NS nameserver1
RR1 = @ IN NS nameserver2
RR2 = domain.com. 3600 IN A 192.168.0.1
RR3 = domain.com. IN MX 100 mx.domain.com.
RR4 = mx.domain.com. IN A 192.168.0.1
RR5 = domain.com. 3600 IN A 192.168.0.1
RR6 = *.domain.com. 3600 IN A 10.10.0.1
SOAEXPIRE = 3600000
SOAMINTTL = 172800
SOAREFRESH = 86400
SOARETRY = 7200
SOARNAME = hostmaster.domain.com.
SOASERIAL = 2
SOATTL = 3600
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[SOASERIAL][0] = 2
EOF
```

----
