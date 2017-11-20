# QueryDomainSuggestionList

## DESCRIPTION
Queries a list of available premium domains that match a keyword given in the command.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainSuggestionList` | COMMAND
KEYWORD | 1 | The keyword to which the query results should match to | TEXT
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
SOURCE | 0 | Defines the source the query the results from. Can be `ISPAPI-CATEGORIES` (Returns the categories of the HEXONET suggestion engine), `ISPAPI-SUGGESTIONS` (Uses the HEXONET suggestion engine for the results) or left blank (uses 3rd party suggestion engines for the result, currently only NAMEMEDIA is supported ).   | TEXT
ZONE[0..N] | 0 | Only show domains with a zone stated here | TEXT
IPADDRESS | 0 | Internet Protocol address of the user used to provide location specific suggestions | IPADDRESS
LANGUAGE[0..N] | 0 | Array of language(s) used to provide language specific suggestions. Use ISO 639-1 two character language codes | TEXT
CATEGORY[0..N] | 0 | Array of categories to have suggestions from. Suggestions are not limit to TLDs within the category but instead TLDs within the provided categories are more likely to be suggested. Available categories can be obtained by calling QueryDomainSuggestionList AND having source = `ISPAPI-CATEGORIES`. | TEXT
----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
549 | Command Failed
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500 | Invalid command name
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CURRENCY[0..N] | 0 | N | The currency in which the domain price will be listed | TEXT
DOMAIN[0..N] | 0 | N | The respective domain name | TEXT
PREMIUMCHANNEL[0..N] | 0 | N | The respective premium domain supplier | TEXT
PRICE[0..N] | 0 | N | The price of the domain name | DECIMAL
CATEGORY[0..N] | 0 | N | Only returned if SOURCE is set to `ISPAPI-CATEGORIES`: The respective categories of the HEXONET suggestion engine | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainSuggestionList
CATEGORY0 = shopping,marketing
KEYWORD = coffeeshop
LANGUAGE0 = en
SOURCE = ISPAPI-SUGGESTIONS
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[DOMAIN][0] = coffee.shopping
PROPERTY[DOMAIN][1] = shop.coffee
PROPERTY[DOMAIN][2] = coffeeshop.forsale
PROPERTY[DOMAIN][3] = coffeeshop.sale
PROPERTY[DOMAIN][4] = coffeeshop.reviews
PROPERTY[DOMAIN][5] = coffeeshop.market
PROPERTY[DOMAIN][6] = coffeeshop.gift
PROPERTY[DOMAIN][7] = coffeeshop.com
PROPERTY[DOMAIN][8] = coffeeshop.co
PROPERTY[DOMAIN][9] = shop.kitchen
PROPERTY[DOMAIN][10] = coffee.luxury
PROPERTY[DOMAIN][11] = coffee.luxe
PROPERTY[DOMAIN][12] = shop.wine
PROPERTY[DOMAIN][13] = shop.vodka
PROPERTY[DOMAIN][14] = shop.vin
PROPERTY[DOMAIN][15] = shop.bar
PROPERTY[DOMAIN][16] = shop.beer
PROPERTY[DOMAIN][17] = shop.cafe
PROPERTY[DOMAIN][18] = shop.catering
PROPERTY[DOMAIN][19] = shop.cooking
PROPERTY[DOMAIN][20] = shop.eat
PROPERTY[DOMAIN][21] = shop.farm
...
PROPERTY[DOMAIN][111] = coffee.plus
PROPERTY[DOMAIN][112] = coffee.promo
PROPERTY[DOMAIN][113] = coffee.sale
PROPERTY[DOMAIN][114] = coffee.shoes
PROPERTY[DOMAIN][115] = coffee.xn--czrs0t
PROPERTY[DOMAIN][116] = coffee.xn--g2xx48c
PROPERTY[DOMAIN][117] = coffee.xn--hxt814e
PROPERTY[DOMAIN][118] = coffee.xn--mgbab2bd
PROPERTY[DOMAIN][119] = javabuy.com
PROPERTY[DOMAIN][120] = beveragestore.com
PROPERTY[DOMAIN][121] = teastore.com
PROPERTY[DOMAIN][122] = cupstore.com
PROPERTY[DOMAIN][123] = beveragebuy.com
PROPERTY[DOMAIN][124] = beveragekeeper.com
PROPERTY[DOMAIN][125] = javashop.com
PROPERTY[DOMAIN][126] = javakeeper.com
PROPERTY[DOMAIN][127] = cupmercantileestablishment.com
PROPERTY[DOMAIN][128] = beveragemercantileestablishment.com
PROPERTY[DOMAIN][129] = coffeestore.com
PROPERTY[DOMAIN][130] = coffeemercantileestablishment.com
PROPERTY[DOMAIN][131] = javastore.com
PROPERTY[DOMAIN][132] = teamercantileestablishment.com
PROPERTY[DOMAIN][133] = beverageshop.com
PROPERTY[DOMAIN][134] = javamercantileestablishment.com
EOF
```

----
