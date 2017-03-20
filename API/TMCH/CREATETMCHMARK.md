# CreateTMCHMark

## DESCRIPTION
The command allows to register a trademark and related domain name labels at Trademark Clearinghouse.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateTMCHMark` | COMMAND
ORDER | 0 | Registration order action:<br>`CREATE` - create a registration order<br>`REPLACE` - replace a registration order<br>`UPDATE` - update a registration order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | ID of the registration order  | INT
MARKTYPE | 1 | `TRADEMARK` | TEXT or NULL
MARKNAME | 1 | Trademark name | TEXT or NULL
GOODSANDSERVICES | 0 | Description of goods and services | LONGTEXT or NULL
GOODSANDSERVICES[0..N] | 0 | Description of goods and services | LONGTEXT or NULL
TRADEMARK-JURISDICTION | 1 | Trademark jurisdiction country code | COUNTRY, `AP`, `BX`, `EM`, `EP`, `EU`, `GC`, `IB`, `OA`, `OT`, `QZ`, `WO` or NULL
TRADEMARK-CLASS[0..N] | 1 | Nice classification number (1-45 or 46 for N/A) | INT or NULL
TRADEMARK-REGISTRATIONNUMBER | 0 | Trademark registration number | INT or NULL
TRADEMARK-REGISTRATIONDATE | 1 | Trademark registration date | DATE or NULL
PERIOD | 0 | Trademark registration period in years, default value: `1` | INT or NULL
LABEL[0..N] | 1 | The ASCII form of the domain name label, related to the trademark | TEXT or NULL
LABEL0SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL0CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL1SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL1CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL2SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL2CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL3SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL3CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL4SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL4CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL5SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL5CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL6SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL6CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL7SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL7CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL8SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL8CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
LABEL9SMDINCLUSION | 0 | Flag for TMCH sunrise services: the label is included in the SMD file to be used in sunrise | INT or NULL
LABEL9CLAIMSNOTIFY | 0 | Flag for the claims services, provided by TMCH: registrants will be made aware of mark existance and holders receive notification on registration during the initial period of general availability | INT or NULL
DOCUMENT0TYPE | 0 | Attached document type | `tmLicenseeDecl`, `tmAssigneeDecl`, `tmOther`, `declProofOfUseOneSample`, `proofOfUseOther` or `copyOfCourtOrder`
DOCUMENT0NAME | 0 | Attached document file name | TEXT
DOCUMENT0CONTENT | 0 | Attached document file content, base64 encoded | LONGTEXT
DOCUMENT1TYPE | 0 | Attached document type | `tmLicenseeDecl`, `tmAssigneeDecl`, `tmOther`, `declProofOfUseOneSample`, `proofOfUseOther` or `copyOfCourtOrder`
DOCUMENT1NAME | 0 | Attached document file name | TEXT
DOCUMENT1CONTENT | 0 | Attached document file content, base64 encoded | LONGTEXT
HOLDER0ENTITLEMENT | 1 | Trademark holder's role | `owner`, `co-owner`, `assignee` or NULL
HOLDER0ORGANIZATION | 1 | Trademark holder's organization | TEXT or NULL
HOLDER0STREET | 1 | Trademark holder's street address | TEXT or NULL
HOLDER0CITY | 1 | Trademark holder's city | TEXT or NULL
HOLDER0STATE | 0 | Trademark holder's state | TEXT or NULL
HOLDER0ZIP | 1 | Trademark holder's postal code | TEXT or NULL
HOLDER0COUNTRY | 0 | Trademark holder's country code | COUNTRY or NULL
HOLDER0PHONE | 0 | Trademark holder's phone number | PHONE or NULL
HOLDER0FAX | 0 | Trademark holder's fax number | PHONE or NULL
HOLDER0EMAIL | 1 | Trademark holder's email address | EMAIL or NULL

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
507 | Invalid command format
530 | Authentication failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ID | 0 | 1 | Trademark ID at TMCH | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CreateTMCHMark
GOODSANDSERVICES = test goods and services
HOLDER0CITY = Homburg
HOLDER0COUNTRY = DE
HOLDER0EMAIL = test.address@testmark.com
HOLDER0ENTITLEMENT = owner
HOLDER0FAX = +49.686412345
HOLDER0ORGANIZATION = TESTMARK GmbH
HOLDER0PHONE = +49.6864123456
HOLDER0STREET = Teststr. 27
HOLDER0ZIP = 66424
LABEL0 = testmark-name
MARKNAME = testmark name
MARKTYPE = TRADEMARK
TRADEMARK-CLASS0 = 8
TRADEMARK-JURISDICTION = DE
TRADEMARK-REGISTRATIONDATE = 2016-10-27
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ID][0] = 0005581610090004-1
EOF
```

----

