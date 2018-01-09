![Project Wyvern Logo](https://media.githubusercontent.com/media/ProjectWyvern/wyvern-branding/master/logo/logo-square-red-transparent-200x200.png?raw=true "Project Wyvern Logo")

## Wyvern DAO Proposals (WDPs)

[![https://badges.frapsoft.com/os/mit/mit.svg?v=102](https://badges.frapsoft.com/os/mit/mit.svg?v=102)](https://opensource.org/licenses/MIT) [![Matrix](https://matrix.to/img/matrix-badge.svg)](https://riot.im/app/#/room/#projectwyvern:matrix.org) [![Discord](https://user-images.githubusercontent.com/7288322/34429152-141689f8-ecb9-11e7-8003-b5a10a5fcb29.png)](https://discord.gg/dZZdybs)

### Synopsis

The [Wyvern DAO](https://dao.projectwyvern.com) is charged with furthering the long-term development of the Wyvern Exchange [protocol](https://github.com/ProjectWyvern/wyvern-protocol/blob/master/build/whitepaper.pdf) and governing the [present Exchange instantiation](https://exchange.projectwyvern.com). In order to carry out this task, the DAO was [provided](https://etherscan.io/tx/0x8894de7a6beff93187722f19fa8b02ee217f19067e98b0188203891e8b4f80f2) with about 7% of the WYV token supply and will receive ongoing profits from operation of the Exchange. How these assets are utilized is up to DAO shareholders - holders of the [Wyvern token](https://token.projectwyvern.com) - who can vote in favor of or against proposals for the DAO to execute particular Ethereum transactions.

The Wyvern DAO can take any action representable by an Ethereum transaction. Proposals may be completely in-band - hiring through [Ethlance](https://ethlance.com/), setting bounties through [Gitcoin](https://gitcoin.co/) - or partially out-of-band, perhaps hiring a contractor through a third-party escrow agent who will hold funds and verify job completion. The DAO can interact with on-chain systems directly - for example, purchasing domain names through the [ENS](https://ens.domains/) or trading through the [Etherdelta](https://etherdelta.com) smart contract. Which proposals succeed is entirely up to the DAO shareholders: if a majority vote yea, the proposals passes, if the majority votes nay, it fails. The Wyvern DAO also supports vote delegation, so small shareholders who do not wish to check in frequently or pay gas costs can delegate their votes to a trusted party (but undelegate them at any time should that party take an action with which they disagree).

This repository exists to serve as a structured proposal discussion board. No actions taken here are binding - only actual votes committed to the Ethereum blockchain through the [Wyvern DAO smart contract](https://etherscan.io/address/wyverndao.eth) count - but this may be a useful way to debate potential proposals and informally query shareholders as to their intentions. Any Wyvern shareholder with a modicum of tokens, currently 2000, may [submit a proposal](https://dao.projectwyvern.com/proposals/create) (this limit is in place to prevent spam and can be changed by the DAO). If you don't have that amount, you can still create a proposal suggestion in this repository and ask someone to submit it to the DAO for you.

### Suggesting a Proposal

Copy the [template proposal](wdp-X.md) and fill in details according to your intentions, then open an issue in [this repository](https://github.com/ProjectWyvern/WDPs/issues). We'll try to keep the repository state synchronized with what proposals have passed or failed - so when you've finalized the proposal and submitted it to the DAO, open a pull request, which will be accepted or rejected depending on what the DAO decides. 

This process is partially inspired by the [EIP proposal system](https://github.com/ethereum/EIPs), although modified for use with an on-chain DAO.
