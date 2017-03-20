# StatusTMCHMark

## DESCRIPTION
The command checks the status of a trademark at TMCH and returns its detailed description.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusTMCHMark` | COMMAND
ID | 1 | ID of a trademark at TMCH | TEXT or NULL
ACTION | 0 | Download the trademark status information as an SMD file | `download`

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
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CLASS | 1 | 1 | `TMCHMARK` | TEXT
CREATEDDATE | 0 | 1 | Validity start date | DATETIME
DESCRIPTION | 1 | 1 | Trademark object ID | TEXT
DOCUMENT[0..N]COMMENT[0..N] | 0 | N | Comment to the aligned document | TEXT
DOCUMENT[0..N]DOCTYPE | 0 | N | Aligned document type:<br>`tmLicenseeDecl` - Licensee declaration<br>`tmAssigneeDecl` - Assignee declaration<br>`tmOther` - Trademark, other<br>`declProofOfUseOneSample` - Declaration of proof of use including one single sample<br>`proofOfUseOther` - Proof of use, other<br>`copyOfCourtOrder` - Copy of a court order | TEXT
DOCUMENT[0..N]FILENAME | 0 | N | Document file name | TEXT
DOCUMENT[0..N]FILETYPE | 0 | N | Document file type:<br>`pdf`<br>`jpg` | TEXT
DOCUMENT[0..N]ID | 0 | N | Document ID | TEXT
DOCUMENT[0..N]STATUS | 0 | N | Document status:<br>`new`<br>`verified`<br>`invalid`<br>`expired` | TEXT
EXPIRATIONDATE | 0 | 1 | Validity expiration date | DATETIME
FILENAME | 0 | 1 | SMD file name | TEXT
GOODSANDSERVICES[0..N] | 1 | N | Description of goods and services | TEXT
HOLDER[0..N]CITY | 1 | N | Trademark holder city | TEXT
HOLDER[0..N]COUNTRY | 1 | N | Trademark holder country code | TEXT
HOLDER[0..N]EMAIL | 1 | N | Trademark holder email address | TEXT
HOLDER[0..N]ENTITLEMENT | 1 | N | Holder's role:<br>`assignee`<br>`licensee`<br>`owner` | TEXT
HOLDER[0..N]FAX | 0 | N | Trademark holder fax number | TEXT
HOLDER[0..N]NAME | 0 | N | Trademark holder name | TEXT
HOLDER[0..N]ORGANIZATION | 0 | N | Trademark holder organization name | TEXT
HOLDER[0..N]PHONE | 0 | N | Trademark holder phone number | TEXT
HOLDER[0..N]STATE | 0 | N | Trademark holder state | TEXT
HOLDER[0..N]STREET | 1 | N | Trademark holder street address | TEXT
HOLDER[0..N]ZIP | 1 | N | Trademark holder postal code | TEXT
ID | 1 | 1 | Trademark ID | TEXT
LABEL [0..N] | 1 | N | The ASCII form of the domain name label | TEXT
LABEL[0..N]CLAIMSNOTIFY | 0 | N | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | TEXT
LABEL[0..N]SMDINCLUSION | 0 | N | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | TEXT
MARKNAME | 1 | 1 | Trademark name | TEXT
MARKTYPE | 1 | 1 | `TRADEMARK` | TEXT
PEERUSER | 1 | 1 | List of subusers, which have a control over the given trademark object | TEXT
POUSTATUS | 0 | 1 | Proof of use status:<br>`corrected`<br>`expired`<br>`incorrect`<br>`invalid`<br>`na`<br>`new`<br>`notSet`<br>`valid` | TEXT
REPOSITORY | 1 | 1 | Trademark repository | TEXT
REPOSITORYPEERUSER | 1 | 1 | List of subusers, which have a control over the trademark repository | TEXT
SMD[0..N] | 0 | N | Encoded SMD | TEXT
SMD-ID | 0 | 1 | ID of the SMD file | TEXT
STATUS | 1 | 1 | Trademark registration status:<br>`corrected`<br>`deactivated`<br>`expired`<br>`incorrect`<br>`invalid`<br>`new`<br>`verified` | TEXT
TRADEMARK-CLASS[0..N] | 0 | N | Nice classification number (1-45 or 46 for N/A) | INT
TRADEMARK-JURISDICTION | 1 | 1 | Trademark jurisdiction country code | TEXT
TRADEMARK-REGISTRATIONDATE | 1 | 1 | Trademark registration date | DATETIME
TRADEMARK-REGISTRATIONNUMBER | 1 | 1 | Trademark registration number | TEXT
ULABEL[0..N] | 1 | N | The Unicode form of the domain name label | TEXT
UPDATEDDATE | 0 | 1 | The last update date | DATETIME
USER | 1 | 1 | User name | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusTMCHMark
ID = 0005581309060001-1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CLASS][0] = TMCHMARK
PROPERTY[CREATEDDATE][0] = 2013-09-06 13:23:48.1
PROPERTY[DESCRIPTION][0] = 0005581309060001-1
PROPERTY[EXPIRATIONDATE][0] = 2014-09-06 00:00:00.0
PROPERTY[GOODSANDSERVICES][0] = ISP
PROPERTY[HOLDER0CITY][0] = Homburg
PROPERTY[HOLDER0COUNTRY][0] = DE
PROPERTY[HOLDER0EMAIL][0] = test@hexonet.net
PROPERTY[HOLDER0ENTITLEMENT][0] = owner
PROPERTY[HOLDER0NAME][0] =
PROPERTY[HOLDER0ORGANIZATION][0] = HEXONET GMBH
PROPERTY[HOLDER0STATE][0] =
PROPERTY[HOLDER0STREET][0] = Talstr. 27
PROPERTY[HOLDER0ZIP][0] = 66424
PROPERTY[ID][0] = 0005581309060001-1
PROPERTY[LABEL][0] = testmark
PROPERTY[LABEL0CLAIMSNOTIFY][0] = 1
PROPERTY[LABEL0SMDINCLUSION][0] = 0
PROPERTY[MARKNAME][0] = testmark
PROPERTY[MARKTYPE][0] = TRADEMARK
PROPERTY[PEERUSER][0] =
PROPERTY[POUSTATUS][0] = verified
PROPERTY[REPOSITORY][0] = TMCH-OTE-558
PROPERTY[STATUS][0] = verified
PROPERTY[TRADEMARK-CLASS][0] = 1
PROPERTY[TRADEMARK-CLASS][1] = 2
PROPERTY[TRADEMARK-JURISDICTION][0] = EM
PROPERTY[TRADEMARK-REGISTRATIONDATE][0] = 2011-01-01 00:00:00.0
PROPERTY[TRADEMARK-REGISTRATIONNUMBER][0] = 1231231
PROPERTY[ULABEL][0] = testmark
PROPERTY[UPDATEDDATE][0] = 2013-09-06 13:30:02.0
PROPERTY[USER][0] = test.user
EOF
```

----
