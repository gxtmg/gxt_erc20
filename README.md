# gxt_erc20

| contract      | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| Ownable       | 소유 가능 계약에는 소유자 주소가 있으며 기본 권한 제어를 제공 The Ownable contract has an owner address, and provides basic authorization control |
| ERC20Basic    | ERC20 인터페이스의 단순한 버전 Simpler version of ERC20 interface |
| BasicToken    | 기본 표준 토큰 Basic version of StandardToken, with no allowances. |
| ERC20         | ERC20 interface                                              |
| StandardToken | 기본 표준 토큰을 구현 Implementation of the basic standard token. |
| BurnableToken | 되돌리수 없는 소각(파괴) 가능한 토큰 Token that can be irreversibly burned (destroyed). |
| Token         | 토큰 기본정보 설정, 추가 발행 함수 선언                      |
|               |                                                              |

<br/><br/>



| Contract         | Type | Description                                                  |
| ---------------- | ---- | ------------------------------------------------------------ |
| Name             | Read | 토큰명 (*string* ) Gem Exchange and Trading                  |
| totalSupply      | Read | 총 수량 (*uint256*) 500000000000000000000000000              |
| decimals         | Read | 소수점 단위 (*uint256**) 18*                                 |
| initialSupply    | Read | 초기 공급량 (*uint256*) 500000000000000000000000000          |
| allowedAddresses | Read | 주소의 allowed 여부 ( allowed true면 locked true 라도 전송가능 ) (address) <input> |
| balanceOf        | Read | 주소의 보유량 (address) _owner                               |
| canTransfer      | Read | 주소의 전송가능 여부 (address) _address                      |
| owner            | Read | contract의 owner 주소 (address) [0x0fef4bb795eb29701e71737e1933e257ab8b68d9](https://etherscan.io/address/0x0fef4bb795eb29701e71737e1933e257ab8b68d9) |
| symbol           | Read | 토큰심볼 (string) GXT                                        |
| lockedAddresses  | Read | 주소 락 여부 ( true:전송불가 ) (address) <input>             |
| locked           | Read | 컨트랙트 락 여부 ( true:전체락 ) (bool) False                |
| allowance        | Read | owner가 spender에게 전송을 허락한 토큰 개수 (address) _owner (address) _spender |


<br/><br/>



# **Ownable** : *contract* 

<br/>

### **Description** 

 

The Ownable contract has an owner address, and provides basic authorization control 

<br/> 

### Functions 

 

- ###### Ownable 

  The Ownable constructor sets the original `owner` of the contract to the sender account 

```
    Ownable() 
```

 

- ###### onlyOwner 

  Throws if called by any account other than the owner. 	

```
     onlyOwner () 
```

  

- ######  transferOwnership 

  Allows the current owner to transfer control of the contract to a newOwner. 

```
     transferOwnership(address newOwner) onlyOwner public() 
```
<br/><br/>
 

# **ERC20Basic: *contract*** 

 <br/> 

### Description 

 Simpler version of ERC20 interface 


<br/><br/>


# **BasicToken: *contract*** 

 
### Description 

<br/>

Basic version of StandardToken, with no allowances. 

<br/>

 

### Functions 

 

- ###### allowAddress 

   allowedAddresses will be able to transfer even when locked 

```
    allowAddress(address _addr, bool _allowed) public onlyOwner 
```

 

- ######  lockAddress 

   allowedAddresses will be able to transfer even when locked 

```
    lockAddress(address _addr, bool _locked) public onlyOwner 
```

 

- ######  setLocked  	

```
    setLocked(bool _locked) public onlyOwner 
```

 

- ######  canTransfer 

```
    canTransfer(address _addr) public constant returns (bool) 
```

 

 

- ###### transfer 

   transfer token for a specified address 

```
    transfer(address _to, uint256 _value) public returns (bool) 
```

 

- ###### balanceOf 

   Gets the balance of the specified address 

```
    balanceOf(address _owner) public constant returns (uint256 balance) 
```

 

 

 

 

# **StandardToken: *contract*** 

 

 

## Description 

 

Implementation of the basic standard token 

 

## Functions 

 

- ###### transferFrom 

   Transfer tokens from one address to another 

```
    transferFrom(address _from, address _to, uint256 _value) public returns (bool) 
```

 

 

- ######  approve 

   Approve the passed address to spend the specified amount of tokens on behalf of msg.sender 

```
    approve(address _spender, uint256 _value) public returns (bool) 
```

 

 

- ###### allowance 

   Function to check the amount of tokens that an owner allowed to a spender 

```
    allowance(address _owner, address _spender) public constant returns (uint256 remaining) 
```

 

- ###### increaseApproval 

  approve should be called when allowed[_spender] == 0. 

  To increment allowed value is better to use this function to avoid 2 calls  

```
    increaseApproval(address _spender, uint _addedValue) 
```

 

- ###### decreaseApproval 

```
    decreaseApproval (address _spender, uint _subtractedValue) 
```

 

 

 

# **BurnableToken: *contract*** 

 

### Description 

 

Token that can be irreversibly burned (destroyed). 

 

### Functions 

 

- ###### burn 

  Burns a specific amount of tokens. 

```
     burn (uint256 _value) onlyOwner public 
```

 

  

# **Token: *contract*** 

 

### Description 

토큰 기본정보 설정 

 

### Functions 

 

- ###### Token  

```
    Token () 
```

 

- ###### mintToken  

```
    mintToken(address target, uint256 mintedAmount) onlyOwner
```

 












 
