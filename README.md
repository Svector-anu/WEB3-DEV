SimpleStorage Contract

This is a simple storage contract that stores a number and a list of people with their favorite number.

 Overview

The `SimpleStorage` contract allows you to store a favorite number and manage a list of people with their favorite numbers. It provides functions to store and retrieve the favorite number, as well as add people to the list.

Contract Details

 State Variables

- `uint256 myFavoriteNumber`: Stores the favorite number.
- `struct Person`: A struct representing a person with a favorite number and a name.
- `Person[] public listOfPeople`: An array of `Person` structs to store the list of people.
- `mapping(string => uint256) public nameToFavoriteNumber`: A mapping to store the favorite number associated with a person's name.

Functions

- `function store(uint256 _favoriteNumber) public`: Stores the given favorite number in the `myFavoriteNumber` state variable.
- `function retrieve() public view returns (uint256)`: Retrieves the stored favorite number.
- `function addPerson(string memory _name, uint256 _favoriteNumber) public`: Adds a person with the given name and favorite number to the `listOfPeople` array and updates the `nameToFavoriteNumber` mapping.

Usage

 Deploying the Contract using Remix IDE

To deploy the `SimpleStorage` contract using Remix IDE, follow these steps:

1. Open Remix IDE: Go to [Remix IDE](https://remix.ethereum.org/) in your web browser.

2. Create a New File: In the Remix IDE, create a new file named `SimpleStorage.sol or anything related to storage` .

3. Copy the Contract Code: Copy the entire `SimpleStorage` contract code and paste it into the `SimpleStorage.sol` file in Remix IDE.

    ```solidity
    // filepath: /Users/macbook/Desktop/VSCODE/web3novA/SVECTOR BOT@WEB3NOVA/WEB3 DEV/myweb3project/contracts/SimpleStorage.sol
    // THis is a simple storege contract that stores a number and a list of people with their favorite number
    // SPDX-License-Identifier: MIT

    pragma solidity ^0.8.19;

    contract SimpleStorage {
        uint256 myFavoriteNumber;

        struct Person {
            uint256 favoriteNumber;
            string name;
        }

        Person[] public listOfPeople;

        mapping(string => uint256) public nameToFavoriteNumber;

        function store(uint256 _favoriteNumber) public {
            myFavoriteNumber = _favoriteNumber;
        }

        function retrieve() public view returns (uint256) {
            return myFavoriteNumber;
        }

        function addPerson(string memory _name, uint256 _favoriteNumber) public {
            listOfPeople.push(Person(_favoriteNumber, _name));
            nameToFavoriteNumber[_name] = _favoriteNumber;
        }
    }
    ```

Compile the Contract: 
    - Select the `Solidity Compiler` tab on the left sidebar.
    - Ensure the compiler version is set to `0.8.19`.
    - Click the `Compile SimpleStorage.sol` button.

  Deploy the Contract:
    - Select the `Deploy & Run Transactions` tab on the left sidebar.
    - Ensure the environment is set to `JavaScript VM (London)`.
    - Click the `Deploy` button under the `Deploy` section.

   Interact with the Contract:
    - After deployment, the contract will appear under the `Deployed Contracts` section.
    - You can expand the contract to see the available functions (`store`, `retrieve`, `addPerson`) and interact with them directly from the Remix IDE.


This project is licensed under the MIT License.
