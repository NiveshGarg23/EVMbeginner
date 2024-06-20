# EVMbeginner
Project: Create a Token
Here we created a MyToken contract that will mint tokens and add them to given addresses.
We have declared a few public variables:
 string public token = "SUBSTANCE";  //Token name
 string public symbol = "SUB";   // Token abbreviation
 uint public total_supply = 0;  // total supply of token
Another mapping variable that associates the address with the balances
 mapping (address => uint) public balances;
We have a few functions like Mint for minting the token which takes address and balance as parameter
  function mintTokens(address _recipient, uint _amount) public {
        accountBalances[_recipient] += _amount;
        totalSupply += _amount;
    }
  another function called burn which burns the token, takes two arguments- address and balance
   function burnTokens(address _holder, uint _amount) public {
        if (accountBalances[_holder] >= _amount) {
            accountBalances[_holder] -= _amount;
            totalSupply -= _amount;
        }
    }
    In the above, we have a condition to check whether the token to be burned is less than the tokens present in that address.
