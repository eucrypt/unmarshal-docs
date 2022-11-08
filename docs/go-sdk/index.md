---
title: Go SDK
---
# Unmarshal Go SDK

A Golang SDK to simplify access to Unmarshal APIs

**This project is currently in *BETA***

## Usage Guide

The first step involved is to `go get` this project.

```shell
go get github.com/eucrypt/unmarshal-go-sdk
```

Create an SDK type and pass it your auth key. (To generate an Auth key you will need to create a user account
at [Unmarshal Console](https://console.unmarshal.io/)

```go
package main

import (
	unmarshal "github.com/eucrypt/unmarshal-go-sdk/pkg"
	conf "github.com/eucrypt/unmarshal-go-sdk/pkg/config"
	"github.com/eucrypt/unmarshal-go-sdk/pkg/constants"
)

func main() {
	sdk := unmarshal.NewWithConfig(conf.Config{
		AuthKey:     "<auth key>",
		Environment: constants.Prod,
	})
}
```

There are other options to use your own `http` client if you prefer as well. The SDK is all you now need to query the
unmarshal APIs

```go
//For example to get the current Price of Marsh, you can now:
package main

import (
	unmarshal "github.com/eucrypt/unmarshal-go-sdk/pkg"
	conf "github.com/eucrypt/unmarshal-go-sdk/pkg/config"
	"github.com/eucrypt/unmarshal-go-sdk/pkg/constants"
)

func main() {
	sdk := unmarshal.NewWithConfig(conf.Config{
		AuthKey:     "<auth key>",
		Environment: constants.Prod,
	})

	resp, err := sdk.GetTokenPriceBySymbol("marsh")
}

```

Some functions are chain specific and the chain can be passed in via the `constants.Chain` package

```go
package main

import (
	unmarshal "github.com/eucrypt/unmarshal-go-sdk/pkg"
	conf "github.com/eucrypt/unmarshal-go-sdk/pkg/config"
	"github.com/eucrypt/unmarshal-go-sdk/pkg/constants"
)

func main() {
	sdk := unmarshal.NewWithConfig(conf.Config{
		AuthKey:     "<auth key>",
		Environment: constants.Prod,
	})

	resp, err := sdk.GetTokenCurrentPrice(constants.BSC, "0x2fa5daf6fe0708fbd63b1a7d1592577284f52256")
}

```

## The SDK has support for the following unmarshal API:

### Price Store ([Docs](https://docs.unmarshal.io/openapi/core/tag/Price-Store/))

- Get Price
    - `v1/pricestore/chain/:chain/:address` (`GetTokenCurrentPrice`)
- Get Price at Instant
    - `v1/pricestore/chain/:chain/:address?timestamp=` (`GetTokenPriceAtInstant`)
- Get Price With Symbol
    - `v1/pricestore/:symbol` (`GetTokenPriceBySymbol`)
- Get Gainers
    - `v1/pricestore/chain/:chain/gainers` (`GetTopGainers`)
- Get Losers
    - `v1/pricestore/chain/:chain/losers` (`GetTopLosers`)
- Get LpTokens
    - `v1/pricestore/chain/:chain/lptokens` (`GetLPTokens`)
- Get Price of List of tokens
    - `v1/tokenstore/token/all` (`GetMultipleTokenPrice`)

### Token Details ([Docs](https://docs.unmarshal.io/openapi/core/tag/Token-Store/))

- Get Token With Contract
    - `v1/tokenstore/token/address/:address` (`GetTokenDetailsByContract`)
- Get Token With Symbol
    - `v1/tokenstore/token/symbol/:symbol` (`GetTokenDetailsBySymbol`)
- Get Paginated List Of Tokens
    - `v1/tokenstore/token/all` (`GetTokenList`)

### Assets API ([Docs](https://docs.unmarshal.io/openapi/core/tag/Wallet-APIs/))

- Get List of Assets
    - `v1/:chain/address/:address/assets` (`GetTokenAssets`)
- Get Profit and loss
    - `v2/:chain/address/:address/userData?contract=` (`GetProfitAndLoss`)

### NFT APIs ([Docs](https://docs.unmarshal.io/openapi/core/tag/NFTs/))

- Get NFT assets for an address
    - `v1/:chain/address/:address/nft-assets` (`GetNFTAssetsByAddress`)
- Get NFT Transactions by Address
    - `v1/:chain/address/:address/nft-transactions` (`GetNFTTransactionsByAddress`)
- Get NFT Metadata
    - `v1/:chain/address/:address/details?tokenId=` (`GetNFTDetailsByID`)
- Get NFT Holders using the NFT's Token ID
    - `v1/:chain/address/:address/nftholders?tokenId=` (`GetNFTHolderByID`)

### Transaction APIs ([Docs](https://docs.unmarshal.io/openapi/core/tag/Wallet-APIs/#tag/Wallet-APIs/operation/transaction-history-v-1))

- Get Transaction data for an address
    - `v1/:chain/address/:address/transactions?contract=&page=&pageSize=` (`GetTokenTxns`)
- Get Transactions data for an address V2/Get Transactions with Price data
    - `v2/:chain/address/:address/transactions?contract=&page=&pageSize=` (`GetTokenTxnsV2`)
- Get Transaction details by Transaction ID
    - `v1/:chain/transactions/:txID` (`GetTxnDetails`)

### Protocol APIs ([Docs](https://docs.unmarshal.io/openapi/core/tag/Price-Store/#tag/Price-Store/operation/price-for-lp-tokens))

- Get Protocol Positions for an address
    - `v2/protocols/:protocol/address/:address/positions` (`GetPositions`)
- Get Protocol Pairs
    - `v2/protocols/:protocol/pairs` (`GetPairs`)


