---
title: Api Weightages
---
# API weights
All Unmarshal plans have generous limits on the amount of requests you can make per month. How many included requests you have depends on the plan you have, check the pricing page for more details.
By giving some heavy requests higher weight we ensure that you ONLY pay for what you use and not a cent more - period! This way you get cheap requests for most use-cases while we can protect our systems from abuse by weighing the computationally expensive endpoints.

##Wallet Api's

Path | Weightage
--- | ---
/v1/:chain/address/:address/assets | 20
/v2/:chain/address/:address/userData | 50
/v1/:chain/address/:address/transactions | 5
/v2/:chain/address/:address/transactions | 20
/v1/:chain/transactions/:transactionHash | 1


##NFT Api's

Path | Weightage
--- | ---
/v1/:chain/address/:address/nft-assets | 10
/v1/:chain/address/:address/nft-transactions | 10
/v1/:chain/contract/:address/nft-transactions | 10
/v1/:chain/contract/:address/tokenIds | 10
/v1/:chain/address/:address/nftholders | 10
/v1/:chain/address/:address/details | 10
/v2/:chain/address/:address/details | 10

##Protocol Api's

Path | Weightage
--- | ---
/v2/protocols/:protocols/address/:address/positions | 20
/v2/protocols/:protocols/pairs | 50
/v2/protocols/:protocols/address/:address/lp_transactions | 20

##Price Store Api's

Path | Weightage
--- | ---
/v1/pricestore/chain/:chain/lptokens | 20
/v1/pricestore/chain/:chain/tokens | 20
/v1/pricestore/chain/:chain/gainers | 50
/v1/pricestore/chain/:chain/losers | 50
/v1/pricestore/chain/:chain/:address | 5
/v1/pricestore/:symbol | 5

##Token Store Api's

Path | Weightage
--- | ---
/v1/tokenstore/token/address/:address | 2
/v1/tokenstore/token/symbol/:symbol | 2
/v1/tokenstore/token/all | 50
/v1/tokenstore/token/list | 25

##Top Traders Api's

Path | Weightage
--- | ---
/v2/:pair/top-traders | 50

##Notifications Api's

Path | Weightage
--- | ---
/v1/:channel/subscribe | 5
/v1/:channel/whale-alert/subscribe | 5
/v1/firebase/refresh-token | 5
/v1/:address/unsubscribe | 1
/v1/subscriptions/firebase/unsubscribe | 5
/v1/firebase/test-notification | 1
/v1/subscriptions/firebase/devices/:deviceId/unsubscribe | 5
/v1/subscriptions/webhook/unsubscribe | 5
/v1/firebase/credentials | 1
/v1/receipts | 5
