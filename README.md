# SmartContractManagementProject

This is a Solidity program with a javascript frontend that simulates a gacha machine that accepts ETH as payment. The purpose of this program is showcase my current understanding of Solidity as a programming language (connecting a smart contract to a front end) as well as serve as a referrence to those who are studying Solidity like me. The original code is from MetacrafterChris and here is the link to his repository: https://github.com/MetacrafterChris/SCM-Starter. I simply added some functionalities on top of his work. Please do check out his other projects on his github! 

## Description

This program is a contract written in Solidity for the contract and javascript for the frontend. This contract has you act as a customer using the gacha machine to generate a character name. It allows you to deposite and withdraw into the system as well as generate a random character name provided that you have enough balance. Your balance and character name are updated as changes to them are made using their respective getter and setter functions.


## Getting Started

### Executing program

In order to run this program, you will have to clone my repository first. First open VS Code and then once it is open click the "File" menu button on the top left. A sub menu will appear and from there click "Open Folder...". Select the directory you want to clone the repository into. A warning may appear that asks if you trust the author click on the yes option. Next find the "Terminal" menu button which might be hidden if you cannot see it look for a "..." found in the same row as the "File" menu button. Upon clicking the "..." the "Terminal" menu button will appear as an option. Clicking the "Terminal" menu button and click "New Terminal" on the submenu that opens. This will open a new terminal window around the bottom part of your screen. Inside the terminal window copy and then paste the following command: 
```git clone https://github.com/devangerine/SmartContractManagementProject.git```

Press the enter key and it will start cloning the repository into the directory you have opened.
Next open the root directory of the repository you have cloned.
Click the "File" menu button on the top left. A sub menu will appear and from there click "Open Folder...". Open the directory where you have cloned the repository and select the root folder "SmartContractManagement" then click the "Select Folder" button. 

Close the terminal window you used to clone the repository and open 3 new ones using the same process mentioned before. You can use the + button found the the first terminal window you created as well to create new terminal windows. 

Go to the first terminal window of the three you just created. You can do this by selecting the top most terminal window found the right side of the current terminal window (In my case they are powershell but yours may vary). In that terminal copy and paste the follow command: 
```npm i``` 
Press enter to run the command and install any dependencies you will need.
Once the it has finished installing the dependencies, go to the second terminal you openned which is below the first one listed the right side of the current terminal you are on.

On the second terminal, copy and paste the following command: ```npx hardhat node```
Press enter to execute the command.
This will spinup a local development node wherein you will be deploying the smart contract of this repository on.

Once the command has finished execution, go to the third terminal then copy and then paste the following command:
```npx hardhat run --network localhost scripts/deploy.js```
Press enter to execute the command.
This will deploy the smart contract to the local netwotk you have spunup. 

Once the command has finished execution, go back to the first terminal and then copy and then paste the followuing command:
```npm run dev ```
Press enter to execute the command.
This will compile the frontend and where it will exist on a sort of local network.

Once the command has finished execution, open the front end of the program by going to this url on your browser:
```http://localhost:3000/```

Before you can interact with the program you must first setup up your Metemask. Make sure you have the Metamask plugin installed on your browser, registered an account and have logged in. From here you need to add the local network you have spun up to your Metamask's list of networks. Open Metamask and click on the 3 dots stacked on top of each other foumd on the top right corner of the Metamask window. This will open a submenu. Click "Settings" and you will be tkane to the Settings menu. Inside the Settings menu scroll down to find and click on "Networks". This will show you networks already listed on your Metamask. Click on  the  "Add network" button. This will take you to the Add a network menu. Scroll down and click on "Add a network manually". This will open up a form where will input the details of the network you will add. 




### Contract Compilation
In order to compile the code, click on the "Solidity compiler" tab found in the left-hand sidebar below the button that looks like a magnifying glass. Please make sure the Compiler is set to "0.8.18" (or any other compatible version), and then click on the "Compile ErrorHandling.sol" assuming you named your Solidity contract as such. Otherwise, the button will say "Compile " followed by the name of your Solidity contract. For simplicity's sake I will be referring to the contract you have made as "ErrorHandling.sol" but it will appear on the Remix IDE as how you named the contract.


### Contract Deployment
After the contract has been compiled, you can now deploy the contract by clicking on the "Deploy & run transactions" tab found in the left-hand sidebar below the "Solidity compiler" tab. Select the "ErrorHandling.sol" contract or as how you have named it. After selecting the contract, click on the "Deploy" button.


### Post Contract Deployment
After the contract has been deployed, the contract will be found under "Deployed Contracts". Expand it by clicking the ">" button below "Deployed Contracts". You should see the following buttons: 
* sendLoan - sends a _loanAmount of type unsigned integer to a debtor associated with the user-inputted debtorId of type unsigned integer and sets that debtor's debtorOnCooldown status to true preventing that debtor from receiving any more loans. 
* getCreditorBalance - returns the creditor's current balance. 
* getDebtorBalance - returns the balance of the debtor associated the user-inputted _debtorId of type unsigned integer. 
* debtorCooldownStatus - returns the cooldown of the debtor associated the user-inputted _debtorId of type unsigned integer.
* resetCooldown - sets the debtorOnCooldown status of the debtor associated with the user-inputted _debtorId of type unsigned integer back to false thus allowing that debtor to take another loan.
* triggerAssert - increments the transactionFee state variable to trigger the assert statement that assumes it never changes to demonstrate the function of assert.
* viewTransactionFee - returns the current value of the state variable transactionFee.

These buttons correspond to each of the functions within the contract.
The sendLoan, getDebtorBalance, debtorCooldownStatus, and resetCooldown have input fields beside them.

You can interact with contract with the following actions:

#### I - Getting the balance of the creditor

**Steps on getting the balance of the creditor:**

1.) Find the "getCreditorBalance" button.

2.) Click the "getCreditorBalance" button. The current balance of the creditor will be shown below the button.

#### II - Getting the balance of the debtor

Note: getDebtorBalance has the following error handling:

* A require that the _debtorId parameter be only either equal to 0 or 1 because I limited the number of possible debtors to keep this contract as simple as possible. 

**Steps on getting the balance of the debtor:**

1.) Find the input field beside the "getDebtorBalance" button.

2.) Input a _debtorId in that input field. The _debtorId must only be either a 0 or a 1. (Refer to the error handling list of this function found above.)

3.) Click the "getCreditorBalance" button. The current balance of the creditor will be shown below the button.

#### III - Getting the debtorOnCooldown status of a debtor

Note: debtorOnCooldown has the following error handling:

* A require that the _debtorId parameter be only either equal to 0 or 1 because I limited the number of possible debtors to keep this contract as simple as possible. 

**Steps on getting the debtorOnCooldown status of a debtor:**

1.) Find the input field beside the "debtorOnCooldown" button.

2.) Input a _debtorId in that input field. The _debtorId must only be either a 0 or a 1. (Refer to the error handling list of this function found above.)

3.) Click the "debtorOnCooldown" button. The current debtorOnCooldown status of the debtor associated with the _debtorId you provided will be displayed below. It will be false if the debtor is not cooldown
otherwise true if the debtor is on cooldown and cannot take a loan.

#### IV - Sending a loan
Note: sendLoan has the following error handling:

* An assertion that the transactionFee(state variable of type unsigned integer) is always 10 because under normal operation of the contract the transactionFee does not get changed but the triggerAssert function exists to increment the transactionFee in order to demonstate how assert works which is to throw an error and revert any changes to the state of the contract done before the assertion is executed. 

* A require that the _debtorId parameter be only either equal to 0 or 1 because I limited the number of possible debtors to keep this contract as simple as possible.  

* A require that the debtorOnCooldown element assocaited with the _debtorId is false which means that the debtor associated with the _debtorId not on loaning cooldown as a result of taking a loan recently.

* A revert that gets triggered when the if statement that checks if the creditor's balance is less then the _loanAmount returns true. 

* A revert that gets triggered when the if statement that checks if the debtor's balance is less than the transactionFee returns true.

**Steps on sending a loan:**

**Note: The _debtorId with the value of 1 has 0 balance and will always trigger the revert within tge condtional statement checking that the debtor's balance is greater than the transactionFee.**

1.) Find the input field beside the "sendLoan" button.

2.) Click the input field beside the "sendLoan" button and input a _loanAmount and a _debtorId seprated by a comma (e.g. 60, 0). The _debtorId must only be either a 0 or a 1.

3.) Click the  the "sendLoan" button to send the _loanAmount to the debtor assocaited with the _debtorId you provided. This will fail if debtor's debtorOnCooldown status is true or both/either the debtor and/or the creditor do not have enough balance for the transaction otherwise the loan will be sent successfully.(Refer to the error handling list of this function found above.) You can verify that the loan was sent by clicking the "getCreditorBalance" button and the "getDebtorBalance" button. Use the _debtorId you used here in "sendLoan" as your input for "getDebtorbalance". After the transaction the debtor assocaited with the _debtorId will be put on coolddown and receive loans unless you reset that cooldown more on that later. 

#### V - Using resetCooldown to reset the debtorOnCooldown status of a debtor

Note: debtorOnCooldownStatus has the following error handling:

* A require that the _debtorId parameter be only either equal to 0 or 1 because I limited the number of possible debtors to keep this contract as simple as possible. 

**Steps on Using resetCooldown to reset the debtorOnCooldown status of a debtor:**

1.) Find the "resetCooldown" button.

2.) Input a _debtorId in that input field. The _debtorId must only be either a 0 or a 1. (Refer to the error handling list of this function found above.)

3.) Click the "resetCooldown" button. The current debtorOnCooldown status of the debtor associated with the _debtorId you provided will be set to false thus allow the debtor to receive a loan. You can verify this change by using the debtorOnCooldown function making sure to input the same _debtorId you inputed in resetCooldown to debtorOnCooldown.

#### VI - Getting the value of the transactionFee using viewTransactionFee

**Steps on getting the value of the transactionFee:**

1.) Find the "viewTransactionFee" button.

2.) Click the "viewTransactionFee" button. The value of the transactionFee will be found below the button. It should display 10 if the triggerAssert function has not been used.

#### VII - Using triggerAssert

The sendLoan function has an assertion that the transactionFee(state variable of type unsigned integer) is always 10 because under normal operation of the contract the transactionFee does not get changed but the triggerAssert function exists to increment the transactionFee in order to demonstate how assert works which is to throw an error and revert any changes to the state of the contract done before the assertion is executed.  

In this case, we will be intentionally triggering it through the use of triggerAssert.

**Steps on getting the value of the transactionFee:**

1.) Find the "triggerAssert" button.

2.) Click the "triggerAssert" button. The value of the transactionFee will be incremented by 1. You can verify the change to the transactionFee variable by clicking the viewTransactionFee button.

3.) Try sending a loan. (Refer to the instructions on how to send a loan found in the IV - Sending a loan section of this readme file.) It should fail and throw an error.

#### VII - Using resetTransactionFee to reset the transactionFee to it's default value of 10

1.) Find the "resetTransactionFee" button.

2.) Click the "triggerAssert" button. The value of the transactionFee will set to it's default value of 10. You can verify the change to the transactionFee variable by clicking the viewTransactionFee button.

3.) Try sending a loan. (Refer to the instructions on how to send a loan found in the IV - Sending a loan section of this readme file.) It should succeed and throw no errors. You can verify this by viewing the balances of the creditor and the debtor you send the loan to by using getCreditorBalance and getDebtorBalance respectively. 

## Code explanation and Contract usage Video Walkthrough
Below is the video walkthrough on how to use the contract once you already have it compiled and deployed on the Remix IDE:
https://www.loom.com/share/729d20832a7b4f1c824a6c1f79662c21


## Help

### Compilation failed
Please check if the code inside the .sol file you created in remix matches the code I provided. If it does not match then please copy the code I provided in its entirety and replace the code in the .sol filed that you created in Remix. If it does match and it still will not compile then please check your internet connection or trying a different browser or updating your current browser. 

### Debtor balance did not increase/Creditor balance did not dencrease after sending loan
Please make sure that the _debtorId you provided in the input field beside the "sendLoan" button matches the address you provided the input field beside the "getDebtorBalance" button. If both matches there may have been another error such as: 

The transaction itself failed due to either the debtor being on cooldown.

The creditor does not have enough balance for the transaction.

The debtor does not have enough balance for the transaction.

If the above does not help or cover the issue you are having with regards to this Solidity Contract I made then please feel free to reach me at 201812805@fit.edu.ph or voltairedvx@gmail.com and I will try to help you as soon as I can.


## Authors

Drennix Guerrero @ 201812805@fit.edu.ph

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
