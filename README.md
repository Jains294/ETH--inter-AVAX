# ETH-AVAX intermedite EVM

This Solidity program is a simple token contract that demonstrates the functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description
This project serves the purpose of fulfilling a requirement for ETH + AVAX PROOF: Intermediate EVM Course of Metacrafters
This project demonstrates the use of require(), assert(), and revert() functions in a smart contract
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract Error_Handling
{
    
    uint public balance = 0;

    //Cannot withdraw more than we have as balance
    function withdraw(uint amount) public   {
        require(balance > amount, "Not enough balance to withdraw!");
        balance -= amount;
    }

    //Cannot deposit if balance results in value greater than 500
    function deposit(uint amount) public   {
        balance += amount;
        if (balance > 500) {
            revert("Your balance is exceeding the limit!");
        }
    }

    //Checks if the balance is equals to zero
    function isempty() public view returns (string memory){
        assert(balance == 0);
        return "Sorry! You have no money for the transaction.";
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

# Authors
Akshat Jain(akshat.bal2003@gmail.com)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details 
