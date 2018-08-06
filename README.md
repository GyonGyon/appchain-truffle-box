# AppChain-Truffle-Box

# Installation

## Install truffle

```
npm install -g truffle
```

## Unbox Repository

```
truffle unbox Cryptape/AppChain-Truffle-Box
```

## Install Dependencies

```
npm install
```

# Usage

## Config

You can configure your box in `truffle-appchain.js`.

```js
module.exports = {
  networks: {
    development: {
      host: '127.0.0.1',
      port: 1337,
      network_id: '*', // Match any network id
    },
  },
  contractInfo: {
    chainId: 0,
    privkey: 'private key',
    // validUntilBlock: [block number + 88],
    // nonce: [random int],
    // quota: [999999],
    // version: [0],
  },
}
```

### networks

Set network by `--network [network name]`

One of `host + port` and `provider` should be configured to deploy smart contract to AppChain

### contractInfo

#### chainId [required]

Chain id of AppChain, default to 0.

#### privkey [required]

Your private key to send transaction.

#### nonce [optional]

Use to prevent double-spending, default to random integer from 1 - 100

#### quota [optional]

Similar to gas, default to 99999

#### version [optional]

default to 0

#### validUntilBlock

Similar to timeout, default to `current height + 88`

## Compile

```
truffle compile
```

## Migration

<!-- 在 migrations 目录下参照模板编写编译代码 -->

0.  Add migration scripts in `migration`

1.  Migrate to AppChain
    ```
    npm run migrate
    ```
