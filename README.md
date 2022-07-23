# ND1309 C2 Ethereum Smart Contracts, Tokens and Dapps - Project Starter 
**PROJECT: Decentralized Star Notary Service Project** - For this project, you will create a DApp by adding functionality with your smart contract and deploy it on the public testnet.

## Additional information

1) Your ERC-721 Token Name: `StarToken`

2) Your ERC-721 Token Symbol: `STOK`

3) Version of the Truffle and OpenZeppelin used: latest (2022-07-22), `5.5.22` and `4.6.0`

4) Your Token Address on the Rinkeby Network: `0xa005bb6e059506b29ab9161de6f1d81ff3783361`

[Etherscan](https://rinkeby.etherscan.io/address/0xa005bb6e059506b29ab9161de6f1d81ff3783361)


### ToDo
This Starter Code has already implemented the functionalities you implemented in the StarNotary (Version 2) exercise, and have comments in all the files you need to implement your tasks.



### Dependencies
For this project, you will need to have:
1. **Node and NPM** installed - NPM is distributed with [Node.js](https://www.npmjs.com/get-npm)
```bash
# Check Node version
node -v
# Check NPM version
npm -v
```


2. **Truffle v5.X.X** - A development framework for Ethereum. 
```bash
# Unsinstall any previous version
npm uninstall -g truffle
# Install
npm install -g truffle
# Verify the version
truffle version
```


2. **Metamask: 5.3.1** - If you need to update Metamask just delete your Metamask extension and install it again.


3. [Ganache](https://www.trufflesuite.com/ganache) - Make sure that your Ganache and Truffle configuration file have the same port.


4. **Other mandatory packages**:
```bash
cd app
# install packages
npm install --save  @truffle/hdwallet-provider
npm install --save  openzeppelin-solidity
npm install webpack-dev-server -g
npm install web3
```


### Run the application
1. Clean the frontend 
```bash
cd app
# Remove the node_modules  
# remove packages
rm -rf node_modules
# clean cache
npm cache clean
rm package-lock.json
# initialize npm (you can accept defaults)
npm init
# install all modules listed as dependencies in package.json
npm install
```


2. Start Truffle by running
```bash
# fix SSL issue
export NODE_OPTIONS=--openssl-legacy-provider

# For starting the development console
truffle develop
# truffle console

# For compiling the contract, inside the development console, run:
compile

# For migrating the contract to the local Ethereum network
migrate --reset

# Or deploy to Rinkeby network
migrate --reset --network rinkeby

# For running unit tests the contract, inside the development console, run:
test
```

3. Frontend - Once you are ready to start your frontend, run the following from the app folder:
```bash
export NODE_OPTIONS=--openssl-legacy-provider
cd app
npm run dev
```

Open `http://localhost:8080/` and make sure the Metamask extension is installed, and you are logged into it.

If you are using a private network, make sure you have imported the accounts.

But if you are using the Rinkeby Test Network, make sure you have selected an account with balance.

---

### Important
When you will add a new Rinkeyby Test Network in your Metamask client, you will have to provide:

| Network Name | New RPC URL | Chain ID |
|---|---|---|
|Private Network 1|`http://127.0.0.1:9545/`|1337 |

```javascript
    development: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 9545,            // Standard Ethereum port (default: none)
      network_id: "*",       // Any network (default: none)
    },
    rinkeby: {
      provider: () => new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
      network_id: 4,         // rinkeby's id
    },
```

The chain ID above can be fetched by:
```bash
cd app
node index.js
```

