# ModifyNameserver

## DESCRIPTION
Modifies a Nameserver host in the registry.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyNameserver` | COMMAND
NAMESERVER | 1 | Nameserver Hostname | HOSTNAME
NEWNAMESERVER | 0 | Nameserver Hostname | HOSTNAME
ADDIPADDRESS[0..12] | 0 | Add new IP Address of Hostname | IPADDRESS
DELIPADDRESS[0..12] | 0 | Delete existing IP Address of Hostname | IPADDRESS
IPADDRESS[0..12] | 0 | Assigning new IP Address of Hostname <br> Warning: Using IPADDRESS[0..12] will overwrite ALL existing ip addresses stored with this nameserver. | IPADDRESS or NULL

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
507 | Invalid command format
530 | Authentication failed
531 | Authorization failed
532 | Domain names linked with name server
541 | Invalid attribute value
545 | Object not found
549 | Command failed
552 | Object status does not allow for operation


No properties are returned

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyNameserver
ADDIPADDRESS0 = 1.2.3.6
DELIPADDRESS0 = 1.2.3.4
NAMESERVER = ns186.hexonet.net
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
## NOTES
To update the IP address(es) of a nameserver there are two possibilities: (i) provide all the IP address(es) (including those which were previously set in `AddNameserver` command) in the IPADDRESS[0..N] parameter or (ii) either provide new IP address(es) in ADDIPADDRESS[0..N] parameter which should be added or provide existing IP address(es) in the DELIPADDRESS[0..N] parameter that should be removed.
