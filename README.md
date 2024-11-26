# My entry for the Types of Functions Module - ETH+AVAX Project in Metacrafters
A smart contract with an ERC20 token named 'Steadfast'.

# Description
In this assessment we were tasked to create a smart contract that will have an ERC20 token that should mintable, burnable and transferrable to any user. This smart contract was made with OpenZeppelin Wizard and was ran through Remix IDE.

# Code Details
-For ERC20, we have imported some features from OpenZeppelin in order for our token to be burnable and ownable.
```
import {ERC20Burnable} from "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
...
import {Ownable} from "@openzeppelin/contracts/access/Ownable.sol";
```
- OpenZeppelin created a contract that housed all the imports we made with a constructor inside that housed our token's name, symbol, its ownable access control and permit.
```
contract Steadfast is ERC20, ERC20Burnable, Ownable, ERC20Permit {
    constructor(address initialOwner)
        ERC20("Steadfast", "STF")
        Ownable(initialOwner)
        ERC20Permit("Steadfast")
    {}

```
- We then created the smart contract have a minting function.
```
function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
```
# Author
Lars James Manansala (larsjamesmanansala@gmail.com)
