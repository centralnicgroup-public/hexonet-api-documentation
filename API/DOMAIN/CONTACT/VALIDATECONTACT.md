# ValidateContact

## DESCRIPTION
Validate a existing contact handle or create and validate a new contact from plain data, to order a .AU domain for a private individual from Australia.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ValidateContact` | COMMAND
REGISTRY | 1 | The Registry where the contact should be validated (currently only AU)| `AU`
X-AU-OWNER-ACCEPT-VALIDATION-TERMS | 0 | Accept the terms required to forward the data for validation | TEXT
X-AU-OWNER-IDTYPE | 0 | IDTYPE indicates the data used for validation. Please refer to the [Hexonet Wiki](https://wiki.hexonet.net/wiki/AUValidation#Supported_document_types) for further details. | `1`, `2`, `3`, `4`, `5`, `6`
X-AU-OWNER-DOB | 0 | The Registrants date of birth in the YYYY-MM-DD format. | TEXT
X-AU-OWNER-IDNUMBER | 0 | Required if X-AU-OWNER-IDTYPE is one of the following: `1`, `2`, `3`, `4`, `5` | TEXT
X-AU-OWNER-IDDATE | 0 | Required if X-AU-OWNER-IDTYPE is one of the following: `1`, `2` | TEXT
X-AU-OWNER-IDISSUER | 0 | Required if X-AU-OWNER-IDTYPE is one of the following: `3`, `6` | TEXT
CONTACT | 0 | If a existing contact should be validated, specify the Contact Handle ID here. If you would rather state the contact details and create the contact on the fly, please use the parameters below. | CONTACT
NAME | 0 | Name, separated by space to fill FIRSTNAME and LASTNAME | TEXT or NULL
FIRSTNAME | 0 | Firstname | TEXT or NULL
LASTNAME | 0 | Lastname | TEXT or NULL
STREET | 0 | Street | TEXT
CITY | 0 | City | TEXT
ZIP | 0 | ZIP / Postal Code | TEXT
COUNTRY | 0 | ISO-3166 Country Code | COUNTRY
PHONE | 0 | ITU Phone Number | PHONE or NULL
EMAIL | 0 | Email Address | EMAIL
AUTH | 0 | Authcode / Password | TEXT
TITLE | 0 | Title | TEXT or NULL
MIDDLENAME | 0 | Middlename | TEXT or NULL
ORGANIZATION | 0 | Organization / Company Name | TEXT or NULL
STATE | 0 | State / Province | TEXT or NULL
FAX | 0 | ITU Phone Number | PHONE or NULL
NEW | 0 | Force to create a new contact even if a contact with the same data exists | `0`, `1` or NULL
STREET[0..N] | 0 | Multiple Street Lines | TEXT or NULL
DISCLOSE-ELEMENTS | 0 | Specify which dedicated contact details should be affected by the DISCLOSE parameter setting. If not stated the DISCLOSE parameter affects all possible contact details. Multiple values are possible and have to be separated by a blank space. Possible values are:<br>`NAME`: disclose the name<br>`ORG`: disclose the organization name<br>`ADDR`: disclose street, state, zip, city and country<br>`VOICE`: disclose the phone number<br>`FAX`: disclose the fax number<br>`EMAIL`: disclose the email address | `/^(((NAME|ORG|ADDR|VOICE|FAX|EMAIL)[ ])*(NAME|ORG|ADDR|VOICE|FAX|EMAIL))?$/`
DISCLOSE | 0 | Set to `1` to disclose (publish) the contact details, set to `0` for non-disclosure. This feature is only supported by dedicated registries and by the HEXONET whois server | `0`, `1`

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
CONTACT | 0 | 1 | Newly created or used contact handle ID | TEXT
X-AU-VALIDATED | 0 | 1 | Indicates if the contact was validated | `1`, `0`  
X-AU-VALIDATED-UNTIL | 0 | 1 | Date until the contact validation is valid | DATE

----
## Example

### Command

```
[COMMAND]
COMMAND = ValidateContact
REGISTRY=AU
X-AU-OWNER-ACCEPT-VALIDATION-TERMS = 1
X-AU-OWNER-IDTYPE=4
X-AU-OWNER-IDNUMBER=PP5667788
X-AU-OWNER-DOB=1973-02-16
CONTACT = P-TCN1378880
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CONTACT][0] = P-TCN1378880
PROPERTY[X-AU-VALIDATED][0] = 1
PROPERTY[X-AU-VALIDATED-UNTIL][0] = 2022-08-09 00:00:00
EOF
```

----
