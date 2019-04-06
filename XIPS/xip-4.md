---
xip: 4
title: Frankomoto
author: Christopher Franko (@frankocurrency)
discussions-to: https://github.com/ethereum/EIPs/issues/649
type: Standards Track
category: Core
status: Draft
created: 2019-04-06
discussion: https://github.com/expanse-org/XIPs/issues/4
---

## Simple Summary
Change the mining algorithm to something unique.

## Abstract
2 weeks ago today the expanse network was hit by a reorg attack or more commonly known as a 51% attack. A 51% attack is when an attacker controls 51% of the total hashrate and uses their power to rewrite recent transaction history. In this case the attacker deposited 115k expanse in to bittrex and then rewrote 500 blocks of transaction history data. They were able to pull this off because Expanse currently uses Ethash. Ethash is in abundant supply at a marketplace called Nicehash. By changing the algo that calculates expanse hashes an attacker would have a harder time pulling off the attack and thus making Expanse more secure.

### Goals

 - Stick to the DAG architecture
 - Use hashing functions that are equally as secure as sha3
 - Makes Expanse more unique
 - ASIC resistant

## Motivation
To make Expanse more secure, to make increase the finality of expanse transactions, and to keep GPU mining relevant.

## Specifics

### Basics

Everywhere Keccak512 is used, create a new "Hash512" variable and based on the Epoch determine to use Keccak512 or Sha512 with all new blocks using Sha512.

### Updates in consensus/ethash/algorithim

 - Seed Hash
 - generateCache
 - generateDataset
 - add Frankomoto
 - FrankomotoLight
 - FrankomotoFull

### Updates in other parts of GEXP

Anywhere hashimoto is called, create a if/else block to determine which one to use.

## Implementation
https://github.com/expanse-org/go-expanse/tree/frankomoto_with_blocklock

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
ghts waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
