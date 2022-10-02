# Ducky Vault 🦆

[![Twitter](https://custom-icon-badges.demolab.com/badge/-Follow-blue?style=for-the-badge&logoColor=white&logo=twitter)](https://twitter.com/AadeePatil)
[![GitHub](https://custom-icon-badges.demolab.com/badge/-Follow-orange?style=for-the-badge&logoColor=white&logo=github)](https://github.com/AadeePatil)

This repository contains the core module for a Vault on the [Aptos Network](https://aptoslabs.com/).

## Overview 👀

The module lets users deposit their coins safely into a Vault and then withdraw then at a later point when needed. The module creates a new Vault for each user for each type of coin. Users can only deposit and withdraw from their own Vaults. Dposits and Withdrawls from the Vaults can be paused by the Admin.

> ⚠️ Publisher of the module is the Admin

## Usage ⚙️

### Deposit 🏦

The `deposit<CoinType>(account: &signer, amount: u64)` function can be called to deposit coins into the vault.

```move
public entry fun deposit<CoinType>(
    account: &signer,
    amount: u64
) acquires VaultsInfo, VaultsHolder
```

### Withdraw 💸

The `withdraw<CoinType>(account: &signer, amount: u64)` function can be called to withdraw coins into the vault.

```move
public entry fun withdraw<CoinType>(
    account: &signer,
    amount: u64
) acquires VaultsInfo, VaultsHolder
```

### Pause ⏸️

The `pause(account: &signer)` function can be called by the owner of the module to  pause deposits and withdrawals for all Vaults.

```move
public entry fun pause(account: &signer) acquires VaultsInfo
```

### Unpause ▶️

The `unpause(account: &signer)` function can be called by the owner of the module to  unpause deposits and withdrawals for all Vaults.

```move
public entry fun unpause(account: &signer) acquires VaultsInfo
```

## Test 🧪

The `Vault.move` file also has tests for all the functions of the module.
The tests can be run by running the following command

> ⚠️ You need the [Aptos CLI](https://aptos.dev/cli-tools/aptos-cli-tool/aptos-cli-index/) to run the tests

```bash
aptos move test
```