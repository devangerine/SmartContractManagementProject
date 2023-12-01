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

Before you can interact with the program you must first setup up your Metemask. Make sure you have the Metamask plugin installed on your browser, registered an account and have logged in. From here you need to add the local network you have spun up to your Metamask's list of networks. Open Metamask and click on the 3 dots stacked on top of each other foumd on the top right corner of the Metamask window. This will open a submenu. Click "Settings" and you will be taken to the Settings menu. Inside the Settings menu scroll down to find and click on "Networks". This will show you networks already listed on your Metamask. Click on  the  "Add network" button. This will take you to the Add a network menu. Scroll down and click on "Add a network manually". This will open up a form where will input the details of the network you will add. 

For Network name you can call it whatever you like. 

For New RPC URL: ```http://127.0.0.1:8545/```
This can be found on the second terminal in your VS Code.

For Chain ID: ```31337```

For Currency symbol: ```ETH```

Leave Block explorer URL blank.

After the details above have been added. Click on the "Save" button. 

Close the tab you used to add the network and then open the Metemask plugin again.
Click on the dropwdown on the top left corner of the plugin's window. This will open the up the list of networks and from here select the network you have just added. 

In the contract of this project the first account becomes the owner and will be the only account that has access to the functions of the contract. For this reason you will need to add the account to your Metemask pluigin. 

From here open the Metamask plugin and click on the drop down found at the top senter that says Account followed by a number. This will open up an account list. Click on "Add account or hardware wallet". This will open the add account submenu. Click "import account" and paste this private key ```0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80``` into the input field provided. Click the "Import" button to import the account. Hte private key is of Account 0 which is the first account and the accounts details can be found on the second terminal in your VS Code. 

Open the Metamask plugin and click on the drop down found at the top senter that says Account followed by a number. Click the the account you have just imported. It should have the 92266 at the end of its public key. 

Once you have all this setup you should be ready to use the program.
 
### Program Usage

You can interact with contract with the following actions:

**Note: It is important that you connect your Metamask wallet first using the instructions below in order to gain access to the rest of the functionality of the program."**

#### I - Connecting your Metamask wallet to the program.

**Steps on connecting your Metamask wallet to the program:**

1.) Find the "Please connect your Metamask wallet" button.

2.) Click the "Please connect your Metamask wallet" button. This will open up a menu where you will select which wallet you will link to the program.

3.) Click the "Use Metamask button". This will take you to the main screen of the program.


#### II - Depositing ETH

**Steps on Depositing ETH:**

1.) Find the "Deposit 1 ETH" button.

2.) Click the "Deposit 1 ETH" button. This will open up the Metamask plugin which will be requesting you to confirm the transaction. 

3.) Click the "Confirm" button. Your balance in the program will be increase by 1 ETH.

#### III - Withdrawing ETH

**Steps on Withdrawing ETH:**

1.) Find the "Withdraw 1 ETH" button.

2.) Click the "Withdraw 1 ETH" button. This will open up the Metamask plugin which will be requesting you to confirm the transaction. 

3.) Click the "Confirm" button. Your balance in the program will be dencrease by 1 ETH.

#### IV - Generating a random character name

**Steps on Generating a random character name:**

1.) Find the "Generating a Random Character Name(Costs 1 ETH)" button.

2.) Click the "Generating a Random Character Name(Costs 1 ETH)" button. This will open up the Metamask plugin which will be requesting you to confirm the transaction. 

3.) Click the "Confirm" button. The randomly generated character name will appear beside "Your Random Character Name:" on the page and your balance in the program will be dencrease by 1 ETH as payment for the random character name generation.




## Code explanation and Contract usage Video Walkthrough
Below is the video walkthrough on how to use the program via the frontend after you finished setting everything up:
https://www.loom.com/share/dbc9c953cac740ca8d0c87814e7b4933


## Help

### getBalance() Exception

Please make sure that you are on your Metamask wallet you are using the local network you have added and are using the account you have imported. Another thing you can check is if you have omitted --network localhost form the following comamnd: ```npx hardhat run --network localhost scripts/deploy.js```
when you executed it. It is important to have the part of the command otherwise you will running on an online version instead of your local version. This is because your balance of 10000 ETH is only valid for your local network.

### Nonce Error/ RPC Error

Open your Metamask wallet and click on the 3 dots stacked on top of each other foumd on the top right corner of the Metamask window. This will open a submenu. Click "Settings" and you will be taken to the Settings menu. Click on "Advanced". This will take you the Advanced Settings menu where you will click on the "Clear activity tab data" button. This will open a confirmation prompt. Click on the "Clear" button on the prompt to proceed. From here you should be able to use the program again. 

If the above does not help or cover the issue you are having with regards to this Solidity Contract I made then please feel free to reach me at 201812805@fit.edu.ph or voltairedvx@gmail.com and I will try to help you as soon as I can.


## Authors

Drennix Guerrero @ 201812805@fit.edu.ph

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
