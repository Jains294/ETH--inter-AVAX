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
pragma solidity 0.8.18;

contract MyToken {
    string public token_Name = "PandaPunks";
    string public token_Abbreviation = "PPNKS";
    uint public total_Supply = 0;

    function mint(address recipient, uint256 amount) public {
        require(msg.sender == owner, "Only the owner can mint tokens.");

        total_Supply += amount;
        _mint(recipient, amount);
    }

    function burn(uint256 amount) public {
        require(balanceOf(msg.sender) >= amount, "Insufficient balance to burn.");

        total_Supply -= amount;
        _burn(msg.sender, amount);
    }

    function assert_func() public {
        assert(total_Supply >= 0);
    }

    function revert_func() public {
        if (total_Supply <= 0) {
            revert("Total supply must be greater than zero.");
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

####Authors
Akshat Jain(akshat.bal2003@gmail.com)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details 
