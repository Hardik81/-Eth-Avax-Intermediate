# Transaction Mechanism

This project is a part of final assessment of metacrafters ethereum avalanche intermediate course. In this program we make a transaction mechanism that handles different types of exceptions that can occur during a transaction. We do this with the help of error handling using require(), revert(), assert().

## Description

This project signifies the importance and use of error handling methods such as require(), revert(), assert(). This is prototype of transaction mechanism that we can use to avoid any kind of error while making any transaction. This decreases the chances of loss and can be employed for various other techniques.

## Getting Started

### Executing program

We run this solidity program on compiler named Remix ethereum IDE. This is an online compiler where we can run this program and test working. Link to the compiler: https://remix.ethereum.org/.

Create a new file with + icon available or go to files and add a new file simply. Name your file by going to the pencil icon.
```javascript
pragma solidity ^0.8.13;

contract Transact {
  bool auth=false;
    event account_confirmation(string message);
    event transaction_confirmed(string mess);
    function Get_account(address account, address Confirm,uint amount) public {
      assert(auth);
      require (account==Confirm,"Wrong account");
      emit account_confirmation("Matching/Confirming succesful");
      if (amount >= 100000) {
            revert("Maximum limit for withdrawl or transfer is 100");
        }
        else{
          emit transaction_confirmed("Payment successful");
        }
    }
}

```
What we have done :

1. Define solidity version
2. Make a contract.
3. Set a state for authorisation whether done or not and store as a boolean variable. (In my case I declared auth as boolean variable)
4. Describe events for the messages you wanna get shown after successful transaction.
5. Declare a fuction that takes account, confirm and amount as parameters.
6. In this function we check whether the transaction we are making is authorized or not we can replace this condition for checking captcha etc.
7. After that we check that the address put in account and Confirm fields are same or not. If yes then continue or else the program will raise an error saying "Wrong account".
8. We continue to the if statement wheret we specify a condition to check the amount is greater than the limit of transaction If yes then we revert an message that is "Maximum limit for withdrawl or transfer is 100".
9. Else it the transaction completes successfully and a similar message is shown using event-emit.

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.13" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by trying every type of error possible like mismatching the addresses, entering more than 100000 as amount value and putting authorization state false.

## Authors

Hardik  
@hardikxibscience238@gmail.com
