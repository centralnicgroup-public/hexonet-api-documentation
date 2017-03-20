# CloneContact

## DESCRIPTION
Command to clone an existing contact with all its properties. Additionally single properties can be overwritten by passing them as new parameter.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CloneContact` | COMMAND
CONTACT | 1 | Contact Handle ID | CONTACT
NAME | 0 | Name, separated by space to fill FIRSTNAME and LASTNAME | TEXT or NULL
FIRSTNAME | 0 | Firstname | TEXT or NULL
LASTNAME | 0 | Lastname | TEXT or NULL
STREET | 0 | Street | TEXT
CITY | 0 | City | TEXT
ZIP | 0 | ZIP / Postal Code | TEXT
COUNTRY | 0 | ISO-3166 Country Code | COUNTRY
PHONE | 0 | ITU Phone Number | PHONE or NULL
EMAIL | 0 | Email Address | EMAIL
AUTH | 0 | Authcode | TEXT
TITLE | 0 | Title | TEXT or NULL
MIDDLENAME | 0 | Middlename | TEXT or NULL
ORGANIZATION | 0 | Organization | TEXT or NULL
STATE | 0 | State | TEXT or NULL
FAX | 0 | ITU Phone Number | PHONE or NULL
STREET[0..N] | 0 | Street | TEXT or NULL
VATID | 0 | VAT Number | TEXT or NULL
IDNUMBER | 0 | ID Number / Passport Number | TEXT or NULL
IDAUTHORITY | 0 | ID Authority | TEXT or NULL
X-CAT-DISCLOSE-FLAG | 0 | Global disclose flag | `0` or `1`
X-CAT-DISCLOSE-TYPE[0..N] | 0 | Disclose contact elements | `VOICE` or `EMAIL`
X-CAT-EMAIL-SPONSOR | 0 | Email address of the sponsoring contact | TEXT or NULL
X-CAT-MAINTAINER | 0 | Maintainer | TEXT or NULL
X-CAT-LANG | 0 | Contact language | TEXT or NULL
X-COOP-SPONSOR[0..N] | 0 | Sponsoring contact | TEXT or NULL
X-DE-TYPE | 0 | Type of contact at the .DE registry | `PERSON`, `ORGANIZATION`, `ROLE` or NULL
X-PL-CONSENTFORPUBLISHING | 0 | State if you agree to the .PL Consent for Publishing | `0`, `1` or NULL

----
## RESPONSE

Code | Description
---- | ----
200	| Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
530	| Authentication failed
531	| Authorization failed
540 | Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CONTACT | 1 | 1 | Newly created contact handle ID returned | TEXT
STATUS | 1 | 1 | The status of the newly created contact handle | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CloneContact
CONTACT = P-TCN1378880
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CONTACT][0] = P-TCN1378882
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
