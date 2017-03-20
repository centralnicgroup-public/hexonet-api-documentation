# AddNameserver

## DESCRIPTION
Creates a Nameserver host in the registry.

Some registries store nameserver hosts as dedicated objects. For such registries you need to create nameserver host objects before you can use them. If you own the domain example.com and you would like to use the nameservers ns1.example.com and ns2.example.com you will have to create each of the nameserver host objects with an AddNameserver command. It is necessary to provide the respective IP addresses for each nameserver with the command.

## AVAILABILITY
The parent domain of the nameserver must be within the user account.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AddNameserver` | COMMAND
NAMESERVER | 1 | Name of the nameserver host | NAMESERVER
DOMAIN | 0 | Domain Name | DOMAIN
IPADDRESS[0..12] | 1 | IP-address(es) of the nameserver host | IPADDRESS or NULL

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
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
547 | Invalid command sequence
549 | Command Failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CREATEDDATE | 0 | 1 | Created date of the newly added nameserver | DATETIME
HOST | 0 | 1 | Hostname of the newly created nameserver | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = AddNameserver
IPADDRESS0 = 1.2.3.4
IPADDRESS1 = 1.2.3.5
NAMESERVER = ns186.hexonet.net
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0] = 2016-11-10 05:00:00
PROPERTY[HOST][0] = ns186.hexonet.net
EOF
```

----
