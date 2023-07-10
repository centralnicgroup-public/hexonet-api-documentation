# AddContact

## DESCRIPTION
Create a contact handle to use with a domain name.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AddContact` | COMMAND
NAME | 1 | Name, separated by space to fill FIRSTNAME and LASTNAME | TEXT or NULL
FIRSTNAME | 0 | Firstname | TEXT or NULL
LASTNAME | 0 | Lastname | TEXT or NULL
STREET | 1 | Street | TEXT
CITY | 1 | City | TEXT
ZIP | 1 | ZIP / Postal Code | TEXT
COUNTRY | 1 | ISO-3166 Country Code | COUNTRY
PHONE | 1 | ITU Phone Number | PHONE or NULL
EMAIL | 1 | Email Address | EMAIL
CONTACT | 0 | Contact Handle ID | CONTACT
AUTH | 0 | Authcode / Password | TEXT
TITLE | 0 | Title | TEXT or NULL
MIDDLENAME | 0 | Middlename | TEXT or NULL
ORGANIZATION | 0 | Organization / Company Name | TEXT or NULL
STATE | 0 | State / Province | TEXT or NULL
FAX | 0 | ITU Phone Number | PHONE or NULL
NEW | 0 | Force to create a new contact even if a contact with the same data exists | `0`, `1` or NULL
STREET[0..N] | 0 | Multiple Street Lines | TEXT or NULL
VATID | 0 | Store a VATID | TEXT or NULL
IDNUMBER | 0 | Store a ID Number | TEXT or NULL
IDAUTHORITY | 0 | Authority that has issued the contact's personal or organizational identification number | TEXT or NULL
DISCLOSE | 0 | Set to `1` to disclose (publish) the contact details, set to `0` for non-disclosure. This feature is only supported by dedicated registries and by the HEXONET whois server | `0`, `1`
DISCLOSE-ELEMENTS | 0 | Specify which dedicated contact details should be affected by the DISCLOSE parameter setting. If not stated the DISCLOSE parameter affects all possible contact details. Multiple values are possible and have to be separated by a blank space. Possible values are:<br>`NAME`: disclose the name<br>`ORG`: disclose the organization name<br>`ADDR`: disclose street, state, zip, city and country<br>`VOICE`: disclose the phone number<br>`FAX`: disclose the fax number<br>`EMAIL`: disclose the email address | `/^(((NAME|ORG|ADDR|VOICE|FAX|EMAIL)[ ])*(NAME|ORG|ADDR|VOICE|FAX|EMAIL))?$/`
X-AFNIC-DISCLOSE | 0 | If set to `1` the contact details will get disclosed for domains registered at AFNIC | `0`, `1` or NULL
X-CAT-DISCLOSE-FLAG | 0 | Global disclose flag | `0` or `1`
X-CAT-DISCLOSE-TYPE[0..N] | 0 | Disclose contact elements | `VOICE` or `EMAIL`
X-CAT-EMAIL-SPONSOR | 0 | Email address of the sponsoring contact | TEXT or NULL
X-CAT-MAINTAINER | 0 | Maintainer | TEXT or NULL
X-CAT-LANG | 0 | Contact language | TEXT or NULL
X-COOP-SPONSOR[0..N] | 0 | Sponsoring contact | TEXT or NULL
X-UK-REG-TYPE | 0 | Registrant type | TEXT or NULL
X-DE-TYPE | 0 | Type of contact at the .DE registry | `PERSON`, `ORGANIZATION`, `ROLE` or NULL
----
## RESPONSE

Code | Description
---- | ----
200	| Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425	| Service temporarily locked; usage exceeded
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
530	| Authentication failed
531	| Authorization failed
540	| Attribute value is not unique
541	| Invalid attribute value
549	| Command failed
549 | Invalid characters


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CONTACT | 1 | 1 | Newly created contact returned | TEXT
NEW | 0 | 1 | Indicates if a new contact handle has been created | `1`, `0` or NULL  
STATUS | 0 | 1 | The status of the contact handle | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = AddContact
CITY = Samplecity
COUNTRY = DE
EMAIL = test@example.com
FIRSTNAME = Test
LASTNAME = Contact
PHONE = +49.1234567890
STREET = Samplestreet 42
ZIP = 123456
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CONTACT][0] = P-TCN1378880
PROPERTY[NEW][0] = 1
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
