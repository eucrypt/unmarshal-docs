---
title: JS/TS SDK
---
<div align="center">
    <a align="center" href="https://unmarshal.io" target="_blank">
      <img src="https://raw.githubusercontent.com/eucrypt/brand-assets/master/unmarshal_icons/img_circle.svg" alt="Unmarshal JS SDK" height=200/>
    </a>
    <h1 align="center">Unmarshal SDK (JavaScript / TypeScript)</h1>
  <p>
    A library that gives you access to the powerful Unmarshal Server backend from your JavaScript app.
  </p>
  <br/>
</div>

**Features**:

- Wallet APIs
- Protocol(LP) APIs
- NFTs
- Price Store
- Token Store
- Top Traders
- EVM APIs
- Notifications APIs
- **Modular** package: include only what you need
- Fully **Typescript** ready out-of-the box

## 🚀 Quick start

If you're new to unmarshal, check the [quickstart guide in the official docs](https://docs.unmarshal.io/gettingstarted/) on how to get started.

If you're already familiar with unmarshal and have your server set up. Then follow along to connect your SDK:

## 1. Install unmarshal

The easiest way to integrate the unmarshal SDK into your JavaScript project is through the npm module.

Install the package via `npm`:

```shell
npm install @unmarshal/sdk
```

or `yarn`:

```shell
yarn add @unmarshal/sdk
```

Import unmarshal:

```js
import {Unmarshal, Chain} from "@unmarshal/sdk";
```

## 2. Initialise unmarshal

After your dependency is added, you simply need to create new unmarshal instance by passing your auth key

```javascript
const unmarshal = new Unmarshal({
    apiKey: "YOUR_API_KEY_GOES_HERE"
});
```

# Usage

After initialisation, you can use any unmarshal functionalities via, as described in our [extensive docs](https://docs.unmarshal.io)

```typescript
unmarshal.WalletApi
    .getTokenBalances(Chain.ethereum, "demo.eth")
    .then(({data}) => console.log(data))
```
