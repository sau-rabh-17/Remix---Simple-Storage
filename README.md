# 🔐 Storage Factory Smart Contracts

This repository demonstrates the use of **inheritance**, **contract creation**, and **storage interaction** in Solidity. It includes three smart contracts:

1. `SimpleStorage` – A base contract to store and retrieve favorite numbers.
2. `AddFiveStorage` – Inherits from `SimpleStorage` and overrides its behavior.
3. `StorageFactory` – A factory contract that dynamically deploys `SimpleStorage` contracts and interacts with them.

---

## 📂 Folder Structure

```
contracts/
├── AddFiveStorage.sol
├── SimpleStorage.sol
└── StorageFactory.sol
```

---

## 📜 Contracts Overview

### 1. `SimpleStorage.sol`

A basic storage contract that:

* Stores a `myFavoriteNumber`.
* Maps a `string name` to a `uint256 favoriteNumber`.
* Allows adding people with their name and favorite number.

```solidity
function store(uint256 _favoriteNumber) public virtual;
function retrieve() public view returns (uint256);
function addPerson(string memory _name, uint256 _favoriteNumber) public;
```

---

### 2. `AddFiveStorage.sol`

Inherits `SimpleStorage` and **overrides** the `store` function.
Instead of storing the number directly, it stores `_newNumber + 5`.

```solidity
function store(uint256 _newNumber) public override;
```

---

### 3. `StorageFactory.sol`

A **factory contract** that:

* Dynamically creates instances of `SimpleStorage`.
* Interacts with them using the stored contract list.

#### Key Functions:

```solidity
function createSimpleStorageContract() public;
function sfStore(uint256 index, uint256 number) public;
function sfGet(uint256 index) public view returns (uint256);
```

---

## ✅ Features Demonstrated

* ✅ Inheritance in Solidity
* ✅ Function Overriding using `virtual` and `override`
* ✅ Smart Contract Factory Pattern
* ✅ Dynamic contract deployment
* ✅ Interaction with deployed contract instances
* ✅ Structs, Arrays, and Mappings

---

## 🚀 Getting Started

### Prerequisites

* Node.js
* Hardhat or Foundry (for local development)

### Compile Contracts

```bash
npx hardhat compile
```

### Deploy Locally (Using Hardhat)

```bash
npx hardhat node
npx hardhat run --network localhost scripts/deploy.js
```

---



---

