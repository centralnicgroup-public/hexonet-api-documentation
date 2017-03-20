# StatusNameserver

## DESCRIPTION
Query the status of a nameserver host.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusNameserver` | COMMAND
NAMESERVER | 1 | Name of the nameserver host | NAMESERVER

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
549 | Command Failed
545 | Object not found

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDBY | 1 | 1 | Registrar that registered the domain | TEXT
CREATEDDATE | 1 | 1 | The creation date of the domain | DATE
DOMAIN | 0 | 1 | Parent domain under which the nameserver has been created | DOMAIN
HOST | 0 | 1 | Hostname of the nameserver | TEXT
IPADDRESS[0..12] | 1 | 13 | IP address of the nameserver host | IPADDRESS
PEERUSER | 0 | 1 | Subuserchain of the nameserver object | TEXT
REGISTRAR | 0 | 1 | Registrar which owns the nameserver object | TEXT
REPOSITORY | 0 | 1 | Registrar account on which the object is located | TEXT
STATUS | 0 | 1 | Current status of the nameserver object | TEXT
UPDATEDBY | 1 | 1 | Registrar that updated the domain | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the domain | DATE
USER | 0 | 1 | Owner of the nameserver object | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = StatusNameserver
NAMESERVER = ns186.hexonet.net
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDBY][0] = hexonet
PROPERTY[CREATEDDATE][0] = 2016-11-10 05:00:00
PROPERTY[DOMAIN][0] = hexonet.net
PROPERTY[HOST][0] = ns186.hexonet.net
PROPERTY[IPADDRESS][0] = 1.2.3.5
PROPERTY[PEERUSER][0] = demo.hexonet.net test.user
PROPERTY[REGISTRAR][0] = hexonet
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[REPOSITORYPEERUSER][0] =
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[UPDATEDBY][0] = hexonet
PROPERTY[UPDATEDDATE][0] = 2016-11-10 12:10:13
PROPERTY[USER][0] = test.user
EOF
```

----
