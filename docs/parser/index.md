# Parser-Metabase Utility Tables

## A guide to ease of life utilities built into the Unmarshal Metabase Server

## The Unmarshal Schema

Houses a host of useful information for your various analysing needs. There may be times when your dashboard may require
information like a token or a contract’s symbol or its current live price. The unmarshal schema houses this and a wide
variety of other useful information.

### Tables

#### Live Token Prices (`LIVE_TOKEN_PRICES`):

This table houses a snapshot of the Unmarshal Price Store for usage within Metabase. Updated every 5 minutes, it houses
the latest prices of verified tokens tracked at any time by our services.


<table>
  <tr>
   <td>Name
   </td>
   <td>Type
   </td>
   <td>Significance
   </td>
  </tr>
  <tr>
   <td>updated_at
   </td>
   <td>Timestamp with Timezone
   </td>
   <td>Holds the time the present value last changed. Only updated when the value of any field within is modified
   </td>
  </tr>
  <tr>
   <td>contract_address
   </td>
   <td>text
   </td>
   <td>Contract Addresses of the token
   </td>
  </tr>
  <tr>
   <td>chain_name
   </td>
   <td>text
   </td>
   <td>The name of the chain to which the token belongs.
   </td>
  </tr>
  <tr>
   <td>chain_id
   </td>
   <td>text
   </td>
   <td>The ChainID of the chain to which the token belongs to (where applicable)
   </td>
  </tr>
  <tr>
   <td>price
   </td>
   <td>numeric
   </td>
   <td>The current price in USD
   </td>
  </tr>
  <tr>
   <td>price_change24_h
   </td>
   <td>numeric
   </td>
   <td>The amount of variance in the price of the token in the last 24 hours
   </td>
  </tr>
  <tr>
   <td>price_change_percentage24_h
   </td>
   <td>numeric
   </td>
   <td>The price change in %
   </td>
  </tr>
</table>

#### Token Details (`TOKEN_DETAILS`):

This table house token related metadata such as the symbol, the decimals and the name. It’s a quick and easy way to get
information about a token whose existence is only made aware by a contract address.


<table>
  <tr>
   <td>Name
   </td>
   <td>Type
   </td>
   <td>Significance
   </td>
  </tr>
  <tr>
   <td>updated_at
   </td>
   <td>Timestamp with Timezone
   </td>
   <td>Holds the time the present value last changed. Only updated when the value of any field within is modified
   </td>
  </tr>
  <tr>
   <td>name
   </td>
   <td>text
   </td>
   <td>The name of the token saved
   </td>
  </tr>
  <tr>
   <td>symbol
   </td>
   <td>text
   </td>
   <td>The token’s symbol as saved in its smart contract
   </td>
  </tr>
  <tr>
   <td>contract_address
   </td>
   <td>text
   </td>
   <td>Contract Addresses of the token
   </td>
  </tr>
  <tr>
   <td>decimal
   </td>
   <td>bigint
   </td>
   <td>The number of decimal places to add on to a token when determining its true amount
   </td>
  </tr>
  <tr>
   <td>chain_name
   </td>
   <td>text
   </td>
   <td>The name of the chain to which the token belongs.
   </td>
  </tr>
  <tr>
   <td>chain_id
   </td>
   <td>text
   </td>
   <td>The ChainID of the chain to which the token belongs (where applicable)
   </td>
  </tr>
  <tr>
   <td>total_supply
   </td>
   <td>text
   </td>
   <td>The total available supply of the token as stated when it was created
   </td>
  </tr>
</table>

### Views

#### Complete Token Data(`COMPLETE_TOKEN_DATA`):

This View combines `LIVE_TOKEN_PRICES` and `TOKEN_DETAILS` into a single view to allow common access to available data
in
both the tables.


<table>
  <tr>
   <td>Name
   </td>
   <td>Type
   </td>
   <td>Significance
   </td>
  </tr>
  <tr>
   <td>name
   </td>
   <td>text
   </td>
   <td>The name of the token saved
   </td>
  </tr>
  <tr>
   <td>symbol
   </td>
   <td>text
   </td>
   <td>The token’s symbol as saved in its smart contract
   </td>
  </tr>
  <tr>
   <td>contract_address
   </td>
   <td>text
   </td>
   <td>Contract Addresses of the token
   </td>
  </tr>
  <tr>
   <td>decimal
   </td>
   <td>bigint
   </td>
   <td>The number of decimal places to add on to a token when determining its true amount
   </td>
  </tr>
  <tr>
   <td>chain_name
   </td>
   <td>text
   </td>
   <td>The name of the chain to which the token belongs.
   </td>
  </tr>
  <tr>
   <td>chain_id
   </td>
   <td>text
   </td>
   <td>The ChainID of the chain to which the token belongs (where applicable)
   </td>
  </tr>
  <tr>
   <td>total_supply
   </td>
   <td>text
   </td>
   <td>The total available supply of the token as stated when it was created
   </td>
  </tr>
  <tr>
   <td>price
   </td>
   <td>numeric
   </td>
   <td>The current price in USD
   </td>
  </tr>
  <tr>
   <td>price_change24_h
   </td>
   <td>numeric
   </td>
   <td>The amount of variance in the price of the token in the last 24 hours
   </td>
  </tr>
  <tr>
   <td>price_change_percentage24_h
   </td>
   <td>numeric
   </td>
   <td>The price change in %
   </td>
  </tr>
</table>

### Routines/Functions

The unmarshal schema adds in various Routines or functions that help simplify various requests

#### Getting the live price

The schema includes various functions that help you get the live price of each token saved. The following are some
functions that aid in that effort.

##### With the Symbol (`get_live_price_with_symbol(symbol text)`):

This function returns the live price for the first symbol it sees a match for (sorted in ascending by the chain name)

###### Parameters:

This function accepts a single parameter, `symbol` of type text

###### Return Value:

The function returns a single `numeric` value showcasing the price of the token

###### Modifications:

To get a more specific token’s price, the following self-explanatory functions are also available.

* `get_live_price_with_symbol_and_chain_name(symbol text, chain_name text)`
    * The `chain_name` refers to the similarly named column in [live_token_prices](#live-token-prices-live_token_prices)

* `get_live_price_with_symbol_and_chain_id(symbol text, chain_id text)`
    * The `chain_id` refers to the similarly named column in [live_token_prices](#live-token-prices-live_token_prices)

##### With the Contract Address (`get_live_price_with_contract_address(contract_address text)`):

This function returns the live price for the first `contract_address` it sees a match for (sorted in ascending by the
chain name)

###### Parameters:

This function accepts a single parameter, `contract_address` of type `text`

###### Return Value:

The function returns a single `numeric` value showcasing the price of the token

###### Modifications:

To get a more specific token’s price, the following self-explanatory functions are also available.

* `get_live_price_with_contract_address_and_chain_name(contract_address text, chain_name text)`
    * The `chain_name` refers to the similarly named column in [live_token_prices](#live-token-prices-live_token_prices)

* `get_live_price_with_contract_address_and_chain_id(contract_address text, chain_id text)`
    * The `chain_id` refers to the similarly named column in [live_token_prices](#live-token-prices-live_token_prices)

#### Getting the Symbol:

These are a set of routines made available to fetch the symbol for a given token. All of them require a contract_address
to be passed

##### With just the Contract Address (`get_symbol_with_contract_address(contract_address text)`):

It returns the saved symbol for the given `contract_addresse`. While a collision is usually unlikely, we do provide
routines to make the fetch even more specific

##### Modifications:

* `get_symbol_with_contract_address_and_chain_id(contract_address text, chain_id text)`
    * The `chain_id` refers to the similarly named column in [token_details](#token-details-token_details)

* `get_symbol_with_contract_address_and_chain_name(contract_address text, chain_name text)`
    * The `chain_name` refers to the similarly named column in [token_details](#token-details-token_details)

#### Getting the decimal adjusted value of the Token transferred:

The value of a token transferred may often be misleading to the uninitiated. This set of functions allows a user to get
a decimal adjusted value of a token amount to get a more intuitive sense of the amount involved.

#### With the Contract Address and Chain ID ( `get_decimal_adjusted_value_with_contract_address_and_chain_id(contract_address text, chain_id text, value numeric)`) :

You pass in the `contract_address`, `chain_id` and the amount you want converted. It returns a `numeric` result which
represents the actual decimal value of the transfer.

#### With the Contract Address and Chain Name ( `get_decimal_adjusted_value_with_contract_address_and_chain_id(contract_address text, chain_name text, value numeric)` ) :

You pass in the `contract_address`, `chain_name` and the amount you want converted. It returns a `numeric` result which
represents the actual decimal value of the transfer.
