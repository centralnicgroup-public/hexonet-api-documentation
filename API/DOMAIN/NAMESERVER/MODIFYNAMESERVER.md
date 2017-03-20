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
ADDIPADDRESS[0..12] | 0 | Add new IP Address of Hostname, required if IPADDRESS[0..12] not provided, not required if DELIPADDRESS[0..12] is provided | IPADDRESS
DELIPADDRESS[0..12] | 0 | Delete existing IP Address of Hostname, required if IPADDRESS[0..12] not provided, not required if ADDIPADDRESS[0..12] is provided | IPADDRESS
IPADDRESS[0..12] | 0 | Assigning new IP Address of Hostname, required if ADDIPADDRESS / DELIPADDRESS is not provided<br> Warning: Using IPADDRESS[0..12] will overwrite ALL existing ip addresses stored with this nameserver. | IPADDRESS or NULL

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
