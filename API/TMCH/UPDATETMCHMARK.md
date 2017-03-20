# UpdateTMCHMark

## DESCRIPTION
This command allows to update a trademark data at TMCH.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateTMCHMark` | COMMAND
ID | 1 | Trademark ID | TEXT or NULL
MARKTYPE | 0 | `TRADEMARK` | TEXT or NULL
MARKNAME | 0 | Trademark name | TEXT or NULL
GOODSANDSERVICES | 0 | Description of goods and services | LONGTEXT or NULL
GOODSANDSERVICES[0..N] | 0 | Description of goods and services | LONGTEXT or NULL
TRADEMARK-JURISDICTION | 0 | Trademark jurisdiction country code | COUNTRY, `AP`, `BX`, `EM`, `EP`, `EU`, `GC`, `IB`, `OA`, `OT`, `QZ`, `WO` or NULL
TRADEMARK-CLASS[0..N] | 0 | Nice classification number (1-45 or 46 for N/A) | INT or NULL
TRADEMARK-REGISTRATIONNUMBER | 0 | Trademark registration number | INT or NULL
TRADEMARK-REGISTRATIONDATE | 0 | Trademark registration date | DATE or NULL
HOLDER0ENTITLEMENT | 0 | Holder's role | `owner`, `co-owner`, `assignee` or NULL
HOLDER0ORGANIZATION | 0 | Trademark holder organization name | TEXT or NULL
HOLDER0STREET | 0 | Trademark holder street address | TEXT or NULL
HOLDER0CITY | 0 | Trademark holder city | TEXT or NULL
HOLDER0STATE | 0 | Trademark holder state | TEXT or NULL
HOLDER0ZIP | 0 | Trademark holder postal code | TEXT or NULL
HOLDER0COUNTRY | 0 | Trademark holder country code | COUNTRY or NULL
HOLDER0PHONE | 0 | Trademark holder phone number | PHONE or NULL
HOLDER0FAX | 0 | Trademark holder fax number | PHONE or NULL
HOLDER0EMAIL | 0 | Trademark holder email address | EMAIL or NULL
ADDLABEL[0..N] | 0 | The ASCII form of the domain name label | TEXT or NULL
ADDLABEL0SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL0CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL1SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL1CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL2SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL2CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL3SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL3CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL4SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL4CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL5SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL5CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL6SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL6CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL7SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL7CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL8SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL8CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
ADDLABEL9SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
ADDLABEL9CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
DELLABEL[0..N] | 0 | The ASCII form of the domain name label | TEXT or NULL
ADDDOCUMENT0TYPE | 0 | Aligned document type | `tmLicenseeDecl`, `tmAssigneeDecl`, `tmOther`, `declProofOfUseOneSample`, `proofOfUseOther` or `copyOfCourtOrder`
ADDDOCUMENT0NAME | 0 | Document file name | TEXT
ADDDOCUMENT0CONTENT | 0 | Content of the document file, base64 encoded | LONGTEXT
ADDDOCUMENT1TYPE | 0 | Aligned document type | `tmLicenseeDecl`, `tmAssigneeDecl`, `tmOther`, `declProofOfUseOneSample`, `proofOfUseOther` or `copyOfCourtOrder`
ADDDOCUMENT1NAME | 0 | Document file name | TEXT
ADDDOCUMENT1CONTENT | 0 | Content of the document file, base64 encoded | LONGTEXT

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
545 | Object not found

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = UpdateTMCHMark
HOLDER0CITY = Hamburg
ID = 0005581309060001-1
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

