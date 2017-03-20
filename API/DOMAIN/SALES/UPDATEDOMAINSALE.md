# UpdateDomainSale

## DESCRIPTION
Updates the aftermarket listing (fast-transfer) status or listing parameters for a domain. It is also used to remove a domain listing.

By default the listing status is set to NONE. If an aftermarket requests a listing towards us (e.g. because a customer listed his domain inside his aftermarket account), the status will change from NONE to REQUESTED.

An user in our system can change the status to ACTIVE, telling our system, that the aftermarket listing is valid, or to DISABLED, telling our system that the listing is invalid, and prevent further listing requests.

All LIST-AFTERNIC or LIST-SEDO parameters need to changed at the same time.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ---- | ----
COMMAND | 1 | `UpdateDomainSale` | COMMAND
DOMAIN | 1 | The domain name. | DOMAIN
AFTERNIC-STATUS | 0 | The status on AfterNIC | `DISABLED`, `ACTIVE` or `NONE`
UNLIST-AFTERNIC | 0 | Remove AfterNIC listing | `0` or `1`
LIST-AFTERNIC-LISTINGSTATUS | 0 | The AfterNIC listing status | `2`, `3` or `4`
LIST-AFTERNIC-CURRENCY | 0 | The currency | `USD`
LIST-AFTERNIC-PRICE | 0 | BuyItNow price | `/^[0-9]+(\.[0-9]+)?$/`
LIST-AFTERNIC-MINIMUMOFFER | 0 | The minimum price that you're willing to accept for the domain name from a prospective buyer. | `/^[0-9]+(\.[0-9]+)?$/`
LIST-AFTERNIC-RESERVEPRICE | 0 | The price at which a buyer's bid will be automatically accepted after seven days if no higher bids are received. This price is binding. | `/^[0-9]+(\.[0-9]+)?$/`
LIST-AFTERNIC-FLOORPRICE | 0 | The minimum price for which you are willing to sell the domain name. This price is binding. | `/^[0-9]+(\.[0-9]+)?$/`
LIST-AFTERNIC-TOPCATEGORY | 0 | The top-level category to which the domain name is associated. http://search.afternic.com/taxonomy | TEXT
LIST-AFTERNIC-SECONDLEVELCATEGORY | 0 | The second-level category | TEXT
LIST-AFTERNIC-DESCRIPTION | 0 | A text description of the domain name. | TEXT
SEDO-STATUS | 0 | The listing status on Sedo | `DISABLED`, `ACTIVE` or `NONE`
UNLIST-SEDO | 0 | Remove Sedo listing | `0` or `1`
LIST-SEDO-CURRENCY | 0 | The currency | `USD`, `EUR` or `GBP`
LIST-SEDO-PRICE | 0 | The domain price. If no price is to be set, please set the value as 0 | `/^[0-9]+(\.[0-9]+)?$/`
LIST-SEDO-MINPRICE | 0 | The minimum price for the domain | `/^[0-9]+(\.[0-9]+)?$/`
LIST-SEDO-FORSALE | 0 | optional - `0` = not for sale, `1` = for sale (default) | `0` or `1`
LIST-SEDO-FIXEDPRICE | 0 | `0` = make offer only, `1` = for fixed price domain (default) | `0` or `1`


----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
549 | Channel error

----
## Example

### Command
To list a domain for 1000 USD on both SEDO and AfterNIC:
```
[COMMAND]
COMMAND = UpdateDomainSale
DOMAIN = test12345.com
AFTERNIC-STATUS = ACTIVE
SEDO-STATUS = ACTIVE
LIST-AFTERNIC-CURRENCY = USD
LIST-AFTERNIC-PRICE = 1000.00
LIST-SEDO-CURRENCY = USD
LIST-SEDO-PRICE = 1000.00
EOF
```
### Response

```
[RESPONSE]
DESCRIPTION=Command completed successfully
CODE=200
...
EOF
```

----
