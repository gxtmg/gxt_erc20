# gxt_erc20

Ownable : contract 

  

  

Description 

 

The Ownable contract has an owner address, and provides basic authorization control 

  

Functions 

 

Ownable 

The Ownable constructor sets the original `owner` of the contract to the sender account 

Ownable() 

  

 onlyOwner  

Throws if called by any account other than the owner. 

onlyOwner () 

   

 transferOwnership 

 	Allows the current owner to transfer control of the contract to a newOwner. 

 transferOwnership(address newOwner) onlyOwner public() 

  

  

  

  

 

 

  

ERC20Basic: contract 

  

  

Description 

 Simpler version of ERC20 interface 

  

 

  

BasicToken: contract 

 

  

Description 

 

Basic version of StandardToken, with no allowances. 

  

 

Functions 

 

allowAddress 

 	allowedAddresses will be able to transfer even when locked 

allowAddress(address _addr, bool _allowed) public onlyOwner 

  

 lockAddress 

 	allowedAddresses will be able to transfer even when locked 

lockAddress(address _addr, bool _locked) public onlyOwner 

  

 setLocked 

  	setLocked(bool _locked) public onlyOwner 

  

  canTransfer 

canTransfer(address _addr) public constant returns (bool) 

  

  

transfer 

 	transfer token for a specified address 

transfer(address _to, uint256 _value) public returns (bool) 

  

balanceOf 

 	Gets the balance of the specified address 

balanceOf(address _owner) public constant returns (uint256 balance) 

  

  

 

 

StandardToken: contract 

 

  

Description 

 

Implementation of the basic standard token 

  

Functions 

  

transferFrom 

 	Transfer tokens from one address to another 

transferFrom(address _from, address _to, uint256 _value) public returns (bool) 

 

  

 approve 

 	Approve the passed address to spend the specified amount of tokens on behalf of msg.sender 

approve(address _spender, uint256 _value) public returns (bool) 

 

 

allowance 

 	Function to check the amount of tokens that an owner allowed to a spender 

allowance(address _owner, address _spender) public constant returns (uint256 remaining) 

 

increaseApproval 

approve should be called when allowed[_spender] == 0.  

To increment allowed value is better to use this function to avoid 2 calls 

 	increaseApproval (address _spender, uint _addedValue) 

 

decreaseApproval 

decreaseApproval (address _spender, uint _subtractedValue) 

 

 

 

BurnableToken: contract 

  

Description 

 

Token that can be irreversibly burned (destroyed). 

  

Functions 

 

burn 

Burns a specific amount of tokens. 

 	burn(uint256 _value) onlyOwner public 

 

 

 

 

 

 

 

 

 

 

 

페이지 나누기
 

Token: contract 

  

Description 

토큰 기본정보 설정 

  

Functions 

 

Token 

 	Token () 

 

mintToken 

 	mintToken(address target, uint256 mintedAmount) onlyOwner 

 

 
