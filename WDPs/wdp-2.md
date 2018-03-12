## Preamble

    WDP: [2](https://dao.projectwyvern.com/proposals/2)
    Title: Deploy Wyvern Protocol v2 (part one)
    Author: Protinam <protinam@protonmail.ch>,
            dfinzer <devin.finzer@joinozone.com>,
            Alex Treece <https://twitter.com/alextreece1>
    Status: Passed
    Created: 2018-03-08

## Summary

Start the authorization process for the second version of the Wyvern Protocol.

## Motivation

Wyvern Protocol v2 adds several new features, including an alternative method of fee payment, support for unwrapped (standard) Ether, and gas optimizations.

## Description

Summary of changes from Wyvern Protocol v1:

- Addition of standard (unwrapped) Ether as a payment option for orders. Implemented by a sentinel `paymentToken` value in the order schema (zero-address).
- The use of a proxy contract to authenticate ERC20 `transferFrom` calls, so Exchange users only need to call `approve` once for all future protocol versions.
- The addition of split relayer/protocol fees as an alternative fee method to that of a protocol token. See [here](https://github.com/ProjectWyvern/WDPs/issues/6).
- The addition of a standard "Atomicizer" library to easily serialize multiple transactions, specified by bytecode at runtime, into a single transaction (e.g. a user selling multiple assets as a bundle).
- The addition of a standard "DelegateProxy" contract to proxy an account or contract only able to execute CALLs (not DELEGATECALLs) and allow said account or contract to make use of the "Atomicizer" library. This will be used by the Wyvern DAO.
- A few gas optimizations (mostly avoiding calculating the order hash when unnecessary).

Wyvern Protocol v2 has already [been audited through Solidified](https://github.com/ProjectWyvern/wyvern-ethereum/tree/master/audits/v2) and will additionally be subjected to a public audit during the two-week delay.

The v2 smart contracts have been [deployed to the Ethereum mainnet](https://medium.com/project-wyvern/wyvern-protocol-v2-mainnet-deployment-a87867110e1).

## Transaction Details

Recipient [0xa4306692b00795f97010ec7237980141d08c6D56](https://etherscan.io/address/wyvernproxyregistry.eth)

Bytecode `0xd4e8e063000000000000000000000000b5aa1fb7027290d6d5cbbe3b1aecd5317fa582ec`

Amount `0`

The bytecode can be verified by running the following script in the [wyvern-ethereum](https://github.com/ProjectWyvern/wyvern-ethereum) repository:

```node
const Web3 = require('web3')
const fs = require('fs')

const web3 = new Web3()
const proxyRegistryABI = JSON.parse(fs.readFileSync('./build/contracts/WyvernProxyRegistry.json')).abi
const startGrantAuthentication = proxyRegistryABI.filter(m => m.name === 'startGrantAuthentication')[0]

const encoded = web3.eth.abi.encodeFunctionCall(startGrantAuthentication,
  ['0xb5aa1fb7027290d6d5cbbe3b1aecd5317fa582ec']
)
console.log(encoded)
```

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
