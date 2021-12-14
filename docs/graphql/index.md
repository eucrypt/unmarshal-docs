# GraphQL APIs

![Artboard 7 copy 20@2x (2).png](https://stoplight.io/api/v1/projects/cHJqOjk4NzI0/images/gC5NgDAkmjk)

The GraphQL APIs from Unmarshal allows clients to define the data and execute queries using a query language based on this data type system. The API is not tied to a specific database or storage
engine, but rather leverages code and data on our existing node. Through GraphQL end-point, application builders can access the full capabilities of on-chain data from a single endpoint. The APIs are
backwards compatible, eliminating the risk of rapid changes in RESTful APIs. It allows fetching data precisely avoiding over or under fetching.

## Unmarshal GraphQL API

The GraphQL API is an efficient way for our clients to query and get precise expected results by describing their queries. Our GraphQL API provides a thorough and understandable description of the
data, enables developers to ask for only what they need from blockchains, enables APIs to evolve, and gives developers powerful developer tools to host their decentralized applications easily on any
chain.

**Access GraphQL Playground**

- **Ethereum:** [https://graphql.unmarshal.com/ethereum](https://graphql.unmarshal.com/ethereum)
- **BSC:** [https://graphql.unmarshal.com/bsc](https://graphql.unmarshal.com/bsc)
- **Polygon:** [https://graphql.unmarshal.com/matic](https://graphql.unmarshal.com/matic)

## Blocks

This EndPoint is contains all the geeky details one needs to understand about a block on any chain

**Request**

```gql
{
  blocks(blockNumberDecimal: 13035232) {
  difficulty
  extraData
  gasLimit
  gasUsed
  hash
  logsBloom
  miner
  mixHash
  nonce
  number
  blockNumberDecimal
  parentHash
  receiptsRoot
  sha3Uncles
  size
  stateRoot
  timestamp
  totalDifficulty
  transactionsRoot
  totalConfirmations
}
}
```

**Response**

```json
{
  "data": {
    "blocks": [
      {
        "difficulty": "7807198343184805",
        "extraData": "0xe4b883e5bda9e7a59ee4bb99e9b1bc050025",
        "gasLimit": "29970705",
        "gasUsed": "1396759",
        "hash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "logsBloom": "TJGBjcJQDENXevEFFMapuCFu/NNLW4QlaJs4jv0/f0xoCBVEX38DxJIvUJbPJiWbtgm0hM7JmPPxsgG8nszhS7pn2InkzbgxcKxiMjg39BzMdseFNTshRosPfJ7YgsZyykI5i6Syq62FSl/4kboGP4zFs0KZvinNwrGE3mIpmtwz8qqYPHZ78wu2uRzOTZTZn7GFX3vYE0+xTNa6IrV38Q0XeRNX3CUvPBl/Braryo0z8Wa8BcgqdW/+fgMAqX8AAAD//wEAAP//",
        "miner": "0x829bd824b016326a401d083b33d092293333a830",
        "mixHash": "0xab1886f5654250f4f0b865802cc228dc5bb583b5eb6a2c1d122defd8bb4ca44e",
        "nonce": "0x3853f5000b01e054",
        "number": "0xc6e6e0",
        "blockNumberDecimal": 13035232,
        "parentHash": "0xef66ca4853f2cb85b3fa6c7555bd3b50dfcfc9fe1b1f23ecff60196a6e9d3bf1",
        "receiptsRoot": "0xaae2761ebb8dc7154130d1208b979f3c586a1e9cfe44a041b1eb71e9dc41e85b",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": "5059",
        "stateRoot": "0xf882465ab6e8f9e31ac4bde19b0eb2c61ed7b8d0fa84d79f492cb5e9ae8c6fce",
        "timestamp": 1629102832,
        "totalDifficulty": "29033046781183285654072",
        "transactionsRoot": "0xc104295ebc77fa767c1f97f1ade3605946b64b50f21071e5437ac995018b2400",
        "totalConfirmations": 100
      }
    ]
  }
}
```

## Block Transactions

Want to show transactions block- wise? This End Point lets you fetch all transactions per block

To understand all the transactions on the chain along with block details , this API will be of great assistance. With more granular information on the transaction

**Request**

```gql
{
  transactions(
  blockHash: "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196"
  first: 2
  ) {
  blockHash
  blockNumber
  from
  gas
  gasPrice
  hash
  input
  inputFunction
  nonce
  to
  transactionIndex
  value
  v
  r
  s
  timestamp
  blockNumberDecimal
}
}
```

**Response**

```json
{
  "data": {
    "transactions": [
      {
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "blockNumber": "0xc6e6e0",
        "from": "0xbbed1c61b6e68c397b021c1274080a2005042c08",
        "gas": "120000",
        "gasPrice": "36536135333",
        "hash": "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136",
        "input": "0x112bbd1d",
        "inputFunction": "112bbd1d",
        "nonce": "0x8e1",
        "to": "0xe9a09e0032d1ab5ce4bf09149ef746258252bd0b",
        "transactionIndex": "0x14",
        "value": "0",
        "v": "0x1",
        "r": "0x7d8451dca26cf2093491b409d46ad099dc579773daa356f551e709a9c1ba661a",
        "s": "0x708ee0a2145feef0bfc2c90596d3d0d07fb301b0835f2caf69f076496da8d2ca",
        "timestamp": 1629102832,
        "blockNumberDecimal": 13035232
      },
      {
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "blockNumber": "0xc6e6e0",
        "from": "0x88dcad01503edbcd0795d332f9c3744304a71a15",
        "gas": "174066",
        "gasPrice": "40639217737",
        "hash": "0x63ab1ae67760e6d0448114510e540be1de1981b5b95a395b38abd2763ff729b9",
        "input": "nM65jQNBDETRlHg0m2Q4PGPY8NcbQ4CM0TML+EDBn+7yjRR4h9Ssitwxadwy3uWf7HN4mHVFAwrwdFaDujQzrRfrOQwnFAPf/n9cxCC9/Qy/oW9ZAUUEexLxjjUEjNRZ0ol2MC6VW/W1hxXMREB0JQ0dmWBhAz2bfHDlJnj0PwAAAP//AQAA//8=",
        "inputFunction": "7ff36ab5",
        "nonce": "0x6",
        "to": "0x7a250d5630b4cf539739df2c5dacb4c659f2488d",
        "transactionIndex": "0x13",
        "value": "30684270000000000",
        "v": "0x25",
        "r": "0xe5f46f7c3729f31558cf1ffd0825a44081536fe9eab4a57fa2270213f81f46ad",
        "s": "0x7a256de43ff429637064c8cfb0abc8a314474355483916537438fdf3b6808e3c",
        "timestamp": 1629102832,
        "blockNumberDecimal": 13035232
      }
    ]
  }
}
```

## Transaction Receipts

The details for a transaction confirmation will be available in the Transaction receipt. This End point captures this data precisely.

A blockchain receipt provides proof that some data existed at a specific time, and that the data was approved by the validators of the blockchain. The receipt contains all the information needed to
prove an individual input was indeed part of an approved block.

**Request**

```gql
{
  transactionReceipts(
  transactionHash: "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136"
  ) {
  blockHash
  blockNumber
  cumulativeGasUsed
  from
  gasUsed
  status
  to
  transactionHash
  transactionIndex
  timestamp
  contractAddress
  blockNumberDecimal
}
}
```

**Response**

```json
{
  "data": {
    "transactionReceipts": [
      {
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "blockNumber": "0xc6e6e0",
        "cumulativeGasUsed": "1396759",
        "from": "0xbbed1c61b6e68c397b021c1274080a2005042c08",
        "gasUsed": "87519",
        "status": "0x1",
        "to": "0xe9a09e0032d1ab5ce4bf09149ef746258252bd0b",
        "transactionHash": "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136",
        "transactionIndex": 20,
        "timestamp": 1629102832,
        "contractAddress": "",
        "blockNumberDecimal": 13035232
      }
    ]
  }
}
```

## Transaction Logs

This End Point can give someone the transaction logs for a particular transaction.

```gql
{
  transactionLogs(
  transactionHash: "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136"
  ) {
  address
  topic0
  topic1
  topic2
  topic3
  data
  blockNumber
  transactionHash
  transactionIndex
  blockHash
  logIndex
  removed
  timestamp
  blockNumberDecimal
}
}
```

**Response**

```json
{
  "data": {
    "transactionLogs": [
      {
        "address": "0xe9a09e0032d1ab5ce4bf09149ef746258252bd0b",
        "topic0": "0x0f6068cc0327366c9f8c4d052cf3e449a720815635c94fd32f6cf7b6af710e47",
        "topic1": null,
        "topic2": null,
        "topic3": null,
        "data": "jMvRFcMgDEPRlSQLjBkHGzpDx+8C4TT3V3r44iLzbJYz/XiU5kgYizYaAsuAjmaFwKUPm7nDWoIu89XAjVBKG9NsStIKXeo3yo+fN8dnrNlJPo83TM4xVnj11ncox+35j5PL7IMfAAAA//8BAAD//w==",
        "blockNumber": "0xc6e6e0",
        "transactionHash": "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136",
        "transactionIndex": "0x14",
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "logIndex": 33,
        "removed": false,
        "timestamp": 1629102832,
        "blockNumberDecimal": 13035232
      },
      {
        "address": "0x1e83916ea2ef2d7a6064775662e163b2d4c330a7",
        "topic0": "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
        "topic1": "0x000000000000000000000000e9a09e0032d1ab5ce4bf09149ef746258252bd0b",
        "topic2": "0x000000000000000000000000829bd824b016326a401d083b33d092293333a830",
        "topic3": null,
        "data": "0x00000000000000000000000000000000000000000000001b1977a86c545d83b7",
        "blockNumber": "0xc6e6e0",
        "transactionHash": "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136",
        "transactionIndex": "0x14",
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "logIndex": 32,
        "removed": false,
        "timestamp": 1629102832,
        "blockNumberDecimal": 13035232
      },
      {
        "address": "0xe9a09e0032d1ab5ce4bf09149ef746258252bd0b",
        "topic0": "0x7b567a10ebda9fc8530b066718cc2fa3c6fd42d5df71f9f8bc176ff6673972c3",
        "topic1": null,
        "topic2": null,
        "topic3": null,
        "data": "xM+xGQQhCEThlhhZBi1nHb0arvyLLECS+zOCxwf2tTJxc5fra48NOeH0SCg11fsa7XrPAY0AcMZr/+5rglMZuy165XVMjMy3U/HE6j6zdoYZgbe1j/0AAAD//wEAAP//",
        "blockNumber": "0xc6e6e0",
        "transactionHash": "0x2a7ea461521c969060b8a7b456fe0639ddfde24f0aaa38374bcdb1926eaef136",
        "transactionIndex": "0x14",
        "blockHash": "0xe2e80fdad5ad7763b6092134cbfcc95fde0ff72ac866584a9c1c493c7f960196",
        "logIndex": 31,
        "removed": false,
        "timestamp": 1629102832,
        "blockNumberDecimal": 13035232
      }
    ]
  }
}
```
