# CreateDNSZone

## DESCRIPTION
The command creates a new DNS zone.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateDNSZone` | COMMAND
DNSZONE | 1 | Name of the new zone | TEXT
SOATTL | 0 | TTL value for the whole zone | INT
SOAMNAME | 0 | Master nameserver of the zone; default = ns1.domain.com. | TEXT
SOARNAME | 0 | Responsible person (mailadress with "@" substituted by ".") for the zone; default = hostmaster.domain.com. | TEXT
SOASERIAL | 0 | Value that indicates the "actuality" of the SOA-Record to other nameservers. The soaserial must be increased (or at least incremented) on every zoneupdate; default = 1 | INT
SOAREFRESH | 0 | See the accordant RFC (listed below) for details; default = 86400 | INT
SOARETRY | 0 | See the accordant RFC (listed below) for details; default = 7200 | INT
SOAEXPIRE | 0 | See the accordant RFC (listed below) for details; default = 360000 | INT
SOAMINTTL | 0 | See the accordant RFC (listed below); default = 172800 | INT
RR[0..N] | 0 | A set of desired DNS records (A,NS,MX,PTR,AAAA,TXT) | LONGTEXT
EXTENDED | 0 | Switch to enable extended mode to submit URL and email forwarding records | `0` or `1`
ZONEMODE | 0 | Create the zone as MASTER or SLAVE zone, default is MASTER | `MASTER` or `SLAVE`
SLAVEMASTER | 0 | Master nameserver to replicate the zone from, only required if mode is SLAVE | TEXT or NULL
DOMAINTRANSFER | 0 | Used to create a temporary DNS zone for incoming domain transfers, if no matching domain or PremiumDNS object exists | `0` or `1`


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
531 | Authorization failed
540 | Attribute value is not unique; zone
541 | The command failed

No properties are returned

----
## Example

### Command

```
[COMMAND]
COMMAND = CreateDNSZone
DNSZONE = hexonet.net.
RR0 = @ IN NS ns1
RR1 = @ IN NS ns2
RR2 = hexonet.net. IN A 192.168.0.1
RR3 = hexonet.net. IN MX 100 mail.hexonet.net.
RR4 = www IN A 192.168.0.1
RR5 = mail.hexonet.net. IN A 192.168.0.1
SOAEXPIRE = 3600000
SOAMINTTL = 172800
SOAMNAME = ns1.hexonet.net.
SOAREFRESH = 86400
SOARETRY = 7200
SOARNAME = hostmaster.hexonet.net.
SOASERIAL = 1
SOATTL = 3600
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
EOF
```

----
