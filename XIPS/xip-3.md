---
xip: 3
eip: 1013
title: "Hardfork Meta: Constantinople"
xip author: Christopher Franko
eip author: Nick Savers (@nicksavers)
type: Meta
status: Final
created: 2018-04-20
requires: 145, 609, 1014, 1052, 1234, 1283
---

## Abstract

This meta-EIP specifies the changes included in the Ethereum hardfork named Constantinople.

## Specification

- Codename: Constantinople
- Aliases: Metropolis/Constantinople, Metropolis part 2
- Activation:
  - `Block >= 1,860,000` on the Ethereum mainnet
  - `Block >= 0` on the Aegis testnet
- XIP Changes
  - Reduce block target to 15 seconds from 30 seconds
  - keep block reward the same
  - Introduce Pirl Guard (ignore reorgs greater than 50 blocks)

- Included EIPs:
  - [EIP 145](https://eips.ethereum.org/EIPS/eip-145): Bitwise shifting instructions in EVM
  - [EIP 1014](https://eips.ethereum.org/EIPS/eip-1014): Skinny CREATE2
  - [EIP 1052](https://eips.ethereum.org/EIPS/eip-1052): EXTCODEHASH Opcode
  - [EIP 1234](https://eips.ethereum.org/EIPS/eip-1234): Delay difficulty bomb, adjust block reward
  - [EIP 1283](https://eips.ethereum.org/EIPS/eip-1283): Net gas metering for SSTORE without dirty maps

## References

1. The list above includes the EIPs discussed as candidates for Constantinople at the All Core Dev [Constantinople Session #1](https://github.com/ethereum/pm/issues/55). See also [Constantinople Progress Tracker](https://github.com/ethereum/pm/wiki/Constantinople-Progress-Tracker).
2. https://blog.ethereum.org/2019/02/22/ethereum-constantinople-st-petersburg-upgrade-announcement/

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
