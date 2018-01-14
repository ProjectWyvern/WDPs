## Preamble

    WDP: [0](https://dao.projectwyvern.com/proposals/0)
    Title: Change Board Member Share Threshold to 10 WYV
    Author: Protinam <protinam@protonmail.ch>, MCFX2 (MCFX2 on Riot & Discord)
    Status: Passed
    Created: 2018-01-09

## Summary

Change the board member threshold (amount of WYV tokens required to create proposals) to 10 WYV.

## Motivation

Currently, only users holding 2000 WYV can create proposals in the Wyvern DAO. That unnecessarily limits the actions the DAO may consider taking, as many users with smaller holdings likely have meritable ideas. The threshold was implemented as an antispam measure, but the current Ethereum gas market renders additional antispam measures unnecessary.

## Description

The Wyvern DAO smart contract contains [a threshold number of WYV tokens required to submit proposals](https://github.com/ProjectWyvern/wyvern-ethereum/blob/master/contracts/WyvernDAO.sol#L20). That threshold [can only be changed by the DAO itself](https://github.com/ProjectWyvern/wyvern-ethereum/blob/master/contracts/dao/DelegatedShareholderAssociation.sol#L214). This proposal suggest that the DAO set the threshold to 10 WYV.

## Transaction Details

Recipient [0x17F68886d00845867C154C912b4cCc506EC92Fc7 (wyverndao.eth)](https://etherscan.io/address/wyverndao.eth)

Bytecode `0x6e676b69000000000000000000000000000000000000000000002a5a058fc295ed00000000000000000000000000000000000000000000000000000000000000000010e00000000000000000000000000000000000000000000000008ac7230489e80000`

Amount `0`

The bytecode can be verified by running the following script in the [wyvern-ethereum](https://github.com/ProjectWyvern/wyvern-ethereum) repository:

```node
const Web3 = require('web3')
const fs = require('fs')
const BigNumber = require('bignumber.js')

const web3 = new Web3()
const daoABI = JSON.parse(fs.readFileSync('./build/contracts/WyvernDAO.json')).abi
const changeVotingRules = daoABI.filter(m => m.name === 'changeVotingRules')[0]
const decimals = 18
const token = new BigNumber(10).pow(decimals)

const encoded = web3.eth.abi.encodeFunctionCall(changeVotingRules,
  [token.mul(200000), 60 * 24 * 3, token.mul(10)]
)
console.log(encoded)
```

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
