## Preamble

    WDP: [4](https://dao.projectwyvern.com/proposals/4)
    Title: Deploy Wyvern Protocol v2.1 (part one)
    Author: Protinam <protinam@protonmail.ch>
    Status: Draft
    Created: 2018-06-01

## Summary

Start the authorization process for version 2.1 of the Wyvern Protocol.

## Motivation

Wyvern Protocol v2.1 maintains ABI compatibility with version 2 and adds substantial gas optimizations, cutting settlement prices for most orders nearly in half.

## Description

Summary of changes from Wyvern Protocol v2:

- Heavy EVM optimization of masked bytecode replacement (mostly: performed word-wise rather than byte-wise) and byte array operations. See `contracts/common/ArrayUtils.sol`, mostly rewritten from v2.
- Updated to solc v0.23 (emit before events, some minor syntax changes)
- Updated `zeppelin-solidity` dependency
- Manual (assembly) order hash calculation

Wyvern Protocol v2.1 has already been audited through Solidified ([audic spec](https://github.com/ProjectWyvern/wyvern-ethereum/tree/master/audits/v2.1), [audit results](https://web.solidified.io/contract/5b004d70b0720900110f9dab)).

The v2.1 smart contract has been [deployed to the Ethereum mainnet](https://twitter.com/WyvernProtocol/status/1003011918674550784).

## Transaction Details

Recipient [0xa4306692b00795f97010ec7237980141d08c6D56](https://etherscan.io/address/wyvernproxyregistry.eth)

Bytecode `0xd4e8e0630000000000000000000000006c5e18b3f0c243fc345095960fdb0e7aa61cd02b`

Amount `0`

The bytecode can be verified by running the following script in the [wyvern-ethereum](https://github.com/ProjectWyvern/wyvern-ethereum) repository:

```node
const Web3 = require('web3')
const fs = require('fs')

const web3 = new Web3()
const proxyRegistryABI = JSON.parse(fs.readFileSync('./build/contracts/WyvernProxyRegistry.json')).abi
const startGrantAuthentication = proxyRegistryABI.filter(m => m.name === 'startGrantAuthentication')[0]

const encoded = web3.eth.abi.encodeFunctionCall(startGrantAuthentication,
  ['0x6c5e18b3f0c243fc345095960fdb0e7aa61cd02b']
)
console.log(encoded)
```

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
