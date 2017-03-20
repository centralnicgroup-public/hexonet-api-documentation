# StatusUserClass

## DESCRIPTION
Query information about UserClass.

A UserClass can be used to group relations: Users that have the same conditions, have the same UserClass. Any changes on the UserClass relations affect all users that have this UserClass. UserClass can be set with the USERCLASS parameter at commands AddUser and ModifyUser. The parent users of the user see the USERCLASS at command StatusUser, the user itself only sees the relations produced by the UserClass and not the name of the UserClass.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusUserClass` | COMMAND
USERCLASS | 1 | Name of the user class | TEXT
CONVERT2CURRENCY | 0 | The relation values will be converted into the currency stated here | TEXT

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
541 | Invalid attribute value

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
RELATIONTYPE[0..N] | 0 | N | The respective relation type | TEXT
RELATIONVALUE[0..N] | 0 | N | The respective relation value | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusUserClass
USERCLASS = TEST123
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[RELATIONTYPE][0] = DNSZONE_EXTERNAL_RRS_INCLUDED
PROPERTY[RELATIONTYPE][1] = DNSZONE_HTTP_FORWARDS_INCLUDED
PROPERTY[RELATIONTYPE][2] = DNSZONE_INTERNAL_RRS_INCLUDED
PROPERTY[RELATIONTYPE][3] = DNSZONE_SMTP_FORWARDS_INCLUDED
PROPERTY[RELATIONTYPE][4] = DOMAIN_EU_SCALE_MAXDATE
PROPERTY[RELATIONTYPE][5] = DOMAIN_EU_SCALE_MINDATE
PROPERTY[RELATIONTYPE][6] = PRICE_CLASS_DNSZONE_EXTERNAL_ANNUAL
PROPERTY[RELATIONTYPE][7] = PRICE_CLASS_DNSZONE_EXTERNAL_CURRENCY
PROPERTY[RELATIONTYPE][8] = PRICE_CLASS_DNSZONE_EXTERNAL_RR_ANNUAL
PROPERTY[RELATIONTYPE][9] = PRICE_CLASS_DNSZONE_EXTERNAL_SETUP
PROPERTY[RELATIONTYPE][10] = PRICE_CLASS_DNSZONE_HTTP_ANNUAL
...
PROPERTY[RELATIONVALUE][0] = 10
PROPERTY[RELATIONVALUE][1] = 99999
PROPERTY[RELATIONVALUE][2] = 99999
PROPERTY[RELATIONVALUE][3] = 99999
PROPERTY[RELATIONVALUE][4] = 2011-09-30 23:59:59
PROPERTY[RELATIONVALUE][5] = 2011-08-31 00:00:00
PROPERTY[RELATIONVALUE][6] = 0.30
PROPERTY[RELATIONVALUE][7] = EUR
PROPERTY[RELATIONVALUE][8] = 0.03
PROPERTY[RELATIONVALUE][9] = 0.00
PROPERTY[RELATIONVALUE][10] = 0.00
...
EOF
```

----
