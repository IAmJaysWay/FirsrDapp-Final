# FirstDapp_Final
## Decentralized Voting Dapp

This project  demonstrate how we can build a trusted decentralized Dapp where everyone can vote and we calculate the percentage of votes and show the results using awesome [Web3ui-kit](https://web3uikit.com) .
we use  [HardHat](https://hardhat.org/) framework for developing SmartContract using [Solidity](https://github.com/ethereum/solidity) and testing the smartcontract whether its working properly or not. we use [React.js](https://reactjs.org/) for the frontend .
at the end we use  [Moralis.io](https://moralis.io/) power to wrap the whole Dapp and fetch the data from blockchain and store it in database and get notified whenever a new event is happening.





### Built With

* [React.js](https://reactjs.org/)
* [Node.js](https://nodejs.org/)
* [Moralis.io](https://moralis.io/)
* [HardHat](https://hardhat.org/)
* [Web3UI-KIT](https://web3uikit.com/)


# Quick Start 🚀

*First we need to download `Node.js` depends on your system operation and install it. here is the link [Node.js](https://nodejs.org/)

📄clone `FirstDapp_Final` repo using this command 

```sh
git clone https://github.com/IAmJaysWay/FirsrDapp-Final.git
```

💿 Install all dependencies:
```sh
cd FirstDapp_Final
yarn install 
```

## Install Hardhat 

Run ``` npm i -D hardhat``` in the smartcontract folder.


```sh
npm install dotenv
```

```sh
npm i -D @nomiclabs/hardhat-etherscan
```


## Initialize Hardhat

Run ``` npx hardhat``` in the smartcontract folder.


## Define Environmental Variables

We need to create `.env` file at the main root of our project .and set couple things in there 

1-`API_KEY_POLYGON:` Create api_key  on https://polygonscan.com/myapikey and paste it in `.env`.now we can verify our smartcontract on polygon explorer 

2-`POLYGON_MUMBAI` : In order to connect  `Polygon RPC` you need an account on [Moralis.io](https://moralis.io/) which is free for first Server.

from there you see bunch of endpoints using `Moralis Speedy Nodes` for all EVM chains.copy the related one and paste it on `.env`

3-`DEVELOPMENT_PRIVATE_KEY`: PLEASE BE CAUITIOUS With your private-key and make sure you dont push it here and

USE A WALLET WITH NO FOUND and mention it in `.gitignore` 


## Hardhat Configuration

Go to hardhat.config.js

First in order to be able to verify the smartcontract on etherscan we need to add

```sh
require("@nomiclabs/hardhat-etherscan");
``` 

Second we need to require ```dotenv``` at the start 

```sh
const dotenv = require("@dotenv"); 
dotenv.config(); 
```    

Last we need to define which network we want to use and add the object in ```module.exports```

```
module.exports = {
  solidity: "0.8.7",
  networks: {
    mumbai: {
      url: procces.env.POLYGON_MUMBAI,
      accounts: [process.env.PRIVATE_KEY]

    },
  },
  etherscan: {
    apikey: process.env.API_KEY
  }
};
```

## Compile and Deploy Smartcontract

```sh 
npx hardhat compile
```

```sh
npx hardhat run scripts/deployMarketSentiment.js --network mumbai 
```

notice that you have to rename the default deploy.js script name to whatever your smartcontract name is


## Verify SmartContract

```sh
npx hardhat verify (contract_address_name) --network mumbai
```



## Connect Dapp To Moralis Server

([How to start Moralis Server](https://docs.moralis.io/moralis-server/getting-started/create-a-moralis-server))

After you have your server set up on moralis,locate `index.js` in `src` folder and set your `appid` and `serverid` 

```sh
<MoralisProvider appId="" serverUrl="">
```


Enjoy Learning with Moralis!!





