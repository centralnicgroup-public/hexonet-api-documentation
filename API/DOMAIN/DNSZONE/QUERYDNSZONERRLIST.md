# QueryDNSZoneRRList

## DESCRIPTION
Query a list of Resource Records of a specific DNS Zone

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDNSZoneRRList` | COMMAND
DNSZONE | 1 | DNSZONE to query the list of records out of | TEXT
RR | 0 | Use a pattern to search records, e.g. '@ IN NS ...' | TEXT
RRTYPE | 0 | Return only records of a submitted type, e.g. NS or A | TEXT or NULL
EXTENDED | 0 | Switch to EXTENDED mode to return forwardings | `0` or `1`
SHORT | 0 | Shorten output of records, e.g. parent zone removed from subdomains | `0` or `1`

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
506 | Invalid option value; Syntax error in parameter: DNSZONE
530 | Authentication failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | Number of matching resource records | INT
TOTAL | 1 | 1 | Total number of resource records | INT
RR[0..N] | 0 | N | Returned resource records | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDNSZoneRRList
DNSZONE = testzone123.com.
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[COUNT][0] = 10
PROPERTY[TOTAL][0] = 10
PROPERTY[RR][0] = testzone123.com. 3600 IN SOA ns1.ispapi.net. hostmaster.testzone123.com. 2012040402 86400 7200 3600000 172800
PROPERTY[RR][1] = testzone123.com. 3600 IN NS ns1.ispapi.net.
PROPERTY[RR][2] = testzone123.com. 3600 IN NS ns2.ispapi.net.
PROPERTY[RR][3] = testzone123.com. 3600 IN NS ns3.ispapi.net.
PROPERTY[RR][4] = testzone123.com. 3600 IN A 173.194.35.184
PROPERTY[RR][5] = testzone123.com. 3600 IN MX 10 mail.testzone123.com.
PROPERTY[RR][6] = mail.testzone123.com. 3600 IN A 173.194.35.184
PROPERTY[RR][7] = news.testzone123.com. 3600 IN NS ns1.exacttarget.com.
PROPERTY[RR][8] = news.testzone123.com. 3600 IN NS ns2.exacttarget.com.
PROPERTY[RR][9] = www.testzone123.com. 3600 IN A 173.194.35.184
EOF
```

----
