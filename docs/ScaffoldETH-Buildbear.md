---
sidebar_position: 6
---

# Scaffold-ETH x Buildbear

**Scaffold-Eth x Buildbear** lets you create your own private testnet, (optional) forked from the mainnet, with your own native token and ERC20 Token faucet and blockchain explorer

## 🐻 Features of [Scaffold-ETH x Buildbear](https://github.com/BuildBearLabs/scaffold-eth)


### Creating your private testnet

![image](images/Your%20Private%20Testnet.png)

### Using your personal native token faucet

![image](images/Native%20Token%20Faucet.png)

### Using your personal ERC20 faucet

![image](images/USDC%20Faucet.png)

### Swap your tokens on Forked Uniswap

![image](images/Swap%20Tokens%20Using%20Forked%20Uniswap.png)

## 🏄‍♂️ Quick Start

Prerequisites: [Node (v18 LTS)](https://nodejs.org/en/download/) plus [Yarn (v1.x)](https://classic.yarnpkg.com/en/docs/install/) and [Git](https://git-scm.com/downloads)

🚨 If you are using a version < v18 you will need to remove `openssl-legacy-provider` from the `start` script in `package.json`

#### 1️⃣ clone/fork 🏗 scaffold-eth x buildbear:

```bash
git clone https://github.com/BuildBearLabs/scaffold-eth.git
```

#### 2️⃣ install and create your private testnet (forked from the mainnet):

```bash
cd scaffold-eth
yarn install
yarn fork-bb
```

#### 3️⃣ 🛰 deploy your SwapOnUniswap Contract:

```bash
cd scaffold-eth
yarn deploy
```

#### 4️⃣ start your 📱 frontend:

🚨 if you have not created your private testnet please follow the the steps in point 2 above:

```bash
cd scaffold-eth
yarn start
```


#### 5️⃣ you can use your 🚰 faucet directly from the terminal after creating your private tesnet:

```bash
# for native tokens
yarn faucet-bb native <Insert Amount (optional)> <Insert Your Wallet Address>

# for erc20 tokens
yarn faucet-bb USDC <Insert Amount (optional)> <Insert Your Wallet Address>

# Please note the supported ERC20 tokens below

# by default faucet mints 100 native / erc20 tokens
```

### Supported ERC20 tokens that can be used :

1. USDC
2. USDT
3. DAI
4. BNB
5. BUSD
6. MATIC
7. WBTC
8. UNI
9. AAVE



Please note the address for each ERC20 Tokens is automatically updated / changed based on the network that you have forked from



🔏 Edit your smart contracts in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

💼 Edit your deployment scripts in `packages/hardhat/deploy`

📱 Open [http://localhost:3000](http://localhost:3000) to see the app

<!-- 🚨📡 To deploy to a public domain, use `yarn surge`. You will need to have a surge account and have the surge CLI installed. There is also the option to deploy to IPFS using `yarn ipfs` and `yarn s3` to deploy to an AWS bucket 🪣 There are scripts in the `packages/react-app/src/scripts` folder to help with this.` -->


# 💬 Support Chat

Join the telegram [support chat 💬](https://t.me/Web3_dApp_Developers) or buidlguidl [discord](https://discord.gg/pRsr6rwG) to ask questions and find others building with 🏗 scaffold-eth!