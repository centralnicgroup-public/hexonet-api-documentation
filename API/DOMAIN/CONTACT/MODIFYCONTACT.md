# ModifyContact

## DESCRIPTION
Command to update one or multiple properties of an existing contact handle.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyContact` | COMMAND
CONTACT | 1 | Contact Handle ID | CONTACT
NAME | 0 | Name | TEXT or NULL
TITLE | 0 | Title | TEXT or NULL
FIRSTNAME | 0 | Firstname | TEXT or NULL
MIDDLENAME | 0 | Middlename | TEXT or NULL
LASTNAME | 0 | Lastname | TEXT or NULL
ORGANIZATION | 0 | Organization | TEXT or NULL
STREET | 0 | street | TEXT or NULL
CITY | 0 | City | TEXT or NULL
STATE | 0 | State / Province | TEXT or NULL
ZIP | 0 | Zip / Postal Code | TEXT or NULL
COUNTRY | 0 | ISO-3166 Country Code | COUNTRY or NULL
PHONE | 0 | ITU Phone Number | PHONE or NULL
FAX | 0 | ITU Phone Number | PHONE or NULL
EMAIL | 0 | Email Address | EMAIL or NULL
STREET[0..N] | 0 | Multiple Street Lines | TEXT or NULL
VATID | 0 | VAT ID | TEXT or NULL
IDNUMBER | 0 | ID Number | TEXT or NULL
IDAUTHORITY | 0 | ID Authority | TEXT or NULL
AUTH | 0 | Authcode | TEXT or NULL
DISCLOSE | 0 | Set to `1` to disclose (publish) the contact details, set to `0` for non-disclosure. This feature is only supported by dedicated registries and by the HEXONET whois server | `0`, `1`
DISCLOSE-ELEMENTS | 0 | Specify which dedicated contact details should be affected by the DISCLOSE parameter setting. If not stated the DISCLOSE parameter affects all possible contact details. Multiple values are possible and have to be separated by a blank space. Possible values are:<br>`NAME`: disclose the name<br>`ORG`: disclose the organization name<br>`ADDR`: disclose street, state, zip, city and country<br>`VOICE`: disclose the phone number<br>`FAX`: disclose the fax number<br>`EMAIL`: disclose the email address | `/^(((NAME|ORG|ADDR|VOICE|FAX|EMAIL)[ ])*(NAME|ORG|ADDR|VOICE|FAX|EMAIL))?$/`
X-AFNIC-DISCLOSE | 0 | If set to `1` the contact details will get disclosed for domains registered at AFNIC | `0`, `1` or NULL
X-CAT-DISCLOSE-FLAG | 0 | Global disclose flag | `0` or `1`
X-CAT-DISCLOSE-TYPE[0..N] | 0 | Disclose contact elements | `VOICE` or `EMAIL`
X-CAT-EMAIL-SPONSOR | 0 | Email address of the sponsoring contact | TEXT or NULL
X-CAT-MAINTAINER | 0 | Maintainer | TEXT or NULL
X-CAT-LANG | 0 | Contact language | TEXT or NULL
X-COOP-SPONSOR[0..N] | 0 | Sponsoring contact | TEXT or NULL
X-CZ-DISCLOSE | 0 | Set to `1` to disclose (publish) the contact details, set to `0` for non-disclosure. | `0`, `1`
X-CZ-DISCLOSE-ELEMENTS | 0 | Specify which dedicated contact details should be affected by the DISCLOSE parameter setting. If not stated the DISCLOSE parameter affects all possible contact details. Multiple values are possible and have to be separated by a blank space. Possible values are:<br>`ADDR`: disclose street, state, zip, city and country<br>`VOICE`: disclose the phone number<br>`FAX`: disclose the fax number<br>`EMAIL`: disclose the email address<br>`VAT`: disclose the VAT<br>`IDENT`: disclose the IDENT<br>`NOTIFYEMAIL`: disclose the notification email address | `/^(((ADDR|VOICE|FAX|EMAIL|VAT|IDENT|NOTIFYEMAIL)[ ])*(ADDR|VOICE|FAX|EMAIL|VAT|IDENT|NOTIFYEMAIL))?$/`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425	| Service temporarily locked; usage exceeded
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
506	| Invalid option value
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
545	| Object not found
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyContact
CONTACT = P-TCN1378882
FIRSTNAME = Newname
STREET = Newstreet 42
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
