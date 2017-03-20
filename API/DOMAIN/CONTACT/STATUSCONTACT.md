# StatusContact

## DESCRIPTION
Query the status of a contact object. The command will return all properties a contact object has.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusContact` | COMMAND
CONTACT | 1 | Contact Handle ID | CONTACT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
505 | Invalid attribute value syntax
503 | Invalid attribute name
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
545	| Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
AUTH | 1 | 1 | The handles authorization code | TEXT
CITY | 1 | 1 | City | TEXT
CLASS | 1 | 1 | Class of Object, in case of contact CONTACT is returned | TEXT
COUNTRY | 1 | 1 | 2 letter ISO 3166 Country code | COUNTRY
CREATEDBY | 1 | 1 | Registrar that created the contact | TEXT
CREATEDDATE | 1 | 1 | The creation date of the contact | DATETIME
DESCRIPTION | 1 | 1 | Returns the CONTACT property | TEXT
EMAIL | 1 | 1 | Email address | EMAIL
FAX | 0 | 1 | Fax number | PHONE
FIRSTNAME | 1 | 1 | The first name of the contact | TEXT
ID | 1 | 1 | The contact handle ID | TEXT
LASTNAME | 1 | 1 | The last name of the contact | TEXT
MIDDLENAME | 0 | 1 | The middle name of the contact | TEXT
NAME | 1 | 1 | The name of the contact | TEXT
ORGANIZATION | 1 | 1 | The organization of the contact | TEXT
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PHONE | 1 | 1 | Phone number | PHONE
REGISTRAR | 1 | 1 | Returns the registrar which is the owner of the contact, currently only SYSTEM is returned | TEXT
STATE | 1 | 1 | State or Province | TEXT
STATUS | 1 | 1 | The status of the contact handle | TEXT
STREET | 1 | 1 | Street address | TEXT
TITLE | 0 | 1 | The title of the contact | TEXT
TRANSFERDATE | 1 | 1 | Last transferdate of the contact | DATETIME
UPDATEDBY | 1 | 1 | Registrar that updated the contact | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the contact | DATETIME
USER | 1 | 1 | The user that manages this contact | TEXT
ZIP | 1 | 1 | ZIP or Postal code | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = StatusContact
CONTACT = P-TCN1378880
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[AUTH][0] = 9knrdrb83j
PROPERTY[CITY][0] = Samplecity
PROPERTY[CLASS][0] = CONTACT
PROPERTY[COUNTRY][0] = DE
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-10-04 14:05:47
PROPERTY[DESCRIPTION][0] = P-TCN1378880
PROPERTY[EMAIL][0] = test@example.com
PROPERTY[FAX][0] =
PROPERTY[FIRSTNAME][0] = Test
PROPERTY[ID][0] = P-TCN1378880
PROPERTY[LASTNAME][0] = Contact
PROPERTY[NAME][0] = Test Contact
PROPERTY[ORGANIZATION][0] =
PROPERTY[PEERUSER][0] =
PROPERTY[PHONE][0] = +49.1234567890
PROPERTY[REGISTRAR][0] = SYSTEM
PROPERTY[STATE][0] =
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STREET][0] = Samplestreet 42
PROPERTY[TRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[UPDATEDBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-10-04 14:05:47
PROPERTY[USER][0] = test.user
PROPERTY[ZIP][0] = 123456
EOF
```

----
