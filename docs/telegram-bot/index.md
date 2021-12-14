---
title: Telegram Bot
---
# Unmarshal Telegram Bot

The Unmarshal Telegram is a quick and easy way to get essential blockchain data using simple commands right on telegram.

## Commands:

### `/start`
#### Description:
This command lists out all the various commands the bot supports and various ways of interaction.
#### Usage Example:
`/start` will list out all commands and help data

### `/setfav`
#### Description:
This command allows you to set a favourite token for your `/price` command. In groups, only the admin is allowed to call this value
#### Usage Example:
`/setfav [token symbol]` will set a particular token as your favourite.

**Example:** `/setfav MARSH` will set `$MARSH` as your favourite token.

### `/price`
#### Description:
This command fetches the price of your favourite token by default or the price of any other token provided the symbol as the argument.
#### Usage Example:
`/price` will fetch the price of the token set as your favourite.
`/price [token symbol]` will fetch the price of the given token using its symbol.

**Example**: `/price BNB` will fetch the price of `$BNB`

### `/bal`
#### Description:
This command fetches your token balance provided an address. It fetches your balance on both the `ethereum` and `Binance Smart chain` albeit for only your top two assets.
For any more information, you could use the chain specific version of this command.
#### Usage Example:
`/bal [address]` will fetch the assets balance of an address on both the `ethereum` and `Binance` chains.

**Example**: `/bal 0x71eEAEB679B69D0773adB1923566c8390B10917a` should fetch the assets balance of the provided address.

### `/baleth`
#### Description:
This command fetches your top 4 assets and token balance on the `Ethereum` chain, provided an address.
For any more information, you could visit xscan.io for a complete list of your assets.
#### Usage Example:
`/baleth [address]` will fetch the assets balance of an address on the `ethereum` chain.

**Example**: `/baleth 0x71eEAEB679B69D0773adB1923566c8390B10917a` should fetch the assets balance of the provided address.

### `/balbsc`
#### Description:
This command fetches your top 4 assets and token balance on the `Binance Smart Chain` chain, provided an address.
For more information, you could visit xscan.io for a complete list of your assets.
#### Usage Example:
`/balbsc [address]` will fetch the assets balance of an address on the `Binance` chain.

**Example**: `/balbsc 0x9447e3eD2A23572F7Be359216321f7e67B364BaC` should fetch the assets balance of the provided address.

### `/balmatic`
#### Description:
This command fetches your top 4 assets and token balance on the `Polygon/Matic` chain, provided an address.
For more information, you could visit xscan.io for a complete list of your assets.
#### Usage Example:
`/balmatic [address]` will fetch the assets balance of an address on the `Polygon` chain.

**Example**: `/balmatic 0xc0899474Fa0a2f650231bEfCD5C775C2d9ff04f1` should fetch the assets balance of the provided address.

### `/txn`
#### Description:
This command used with a chain and the transaction ID gives you transaction details. It supports 4 chains and accepts any of the following as chain ID
The following values for chain are accepted:
- _**Ethereum**_ : `ethereum`,  `eth`
- _**Binance**_ : `bsc`,  `binance`
- _**Polygon**/**Matic**_ : `mat`,  `matic`,  `polygon`
#### Usage Example:
The common syntax for usage is:

`/txn [chain] [txn ID/txn signature]`

**Example**:

- `/txn eth 0x6d31131c68dca233240b9f13da313b26d3a33461cb8f8243bb8d57273d14c9b5` for a transaction on the ethereum chain.
- `/txn bsc 0xf32532225a42f7ba7a5db1806b5c924594278744684c894cd00d4ca2973a19a1` for a transaction on the BSC chain.
- `/txn mat 0xd6818c0699cfc5a38ed89a4aa3da9e6df641e884d1642f833178590f7f6f41fe` for a transaction on the Polygon chain.

## `/topgainers`
#### Description:
Fetches the top 3 assets on the Ethereum and Binance chain that have the highest increases in relative price.
#### Usage Example:
`/topgainers` Will fetch a list of the top gainers on ethereum and BSC

## `/toplosers`
#### Description:
Fetches the top 3 assets on the Ethereum and Binance chain that have the highest decreases in relative price.
#### Usage Example:
`/toplosers` Will fetch a list of the top losers on ethereum and BSC

## `/gaseth`
#### Description:
This command fetches the current gas price for a normal eth transfer on the `Ethereum` chain
#### Usage Example:
`/gaseth` Will fetch the current gas price.



