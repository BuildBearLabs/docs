---
sidebar_position: 4
---

# Using Wrapped Matic Contract on the BuildBear’s Polygon Mainnet

Today, we are evaluating the strength of BuildBear’s Forked Mainnet strength to get play with the Wrapped Matic Contract.

**Action Plan**

1. Create a BuildBear Node from a Polygon Mainnet RPC
2. Get 100,000 (One Hundred Thousand Test Tokens; yes that is One HUNDRED THOUSAND) from the Faucet
3. Go to Wrapped Matic Contract
4. Call the `deposit` function

1. **Create a BuildBear Node from a Polygon Mainnet RPC**

(A) Visiting BuildBear ([https://home.buildbear.io/](https://home.buildbear.io/)) to create the node

![Untitled](./UsingWrappedMatic/Untitled.png)

(B) Providing the following as the RPC: [https://polygon-rpc.com](https://polygon-rpc.com/) from where we will be forking the mainnet and then hit the `create` button right at the bottom of the screen

![Untitled](./UsingWrappedMatic/Untitled%201.png)

(C) You should see your Node come up, similar to the following:

![Untitled](./UsingWrappedMatic/Untitled%202.png)

1. **Get 100,000 (One Hundred Thousand Test Tokens; yes that is One HUNDRED THOUSAND) from the Faucet**

(A) Click on the `Open Faucet`, you should arrive at a page similar to the following:

![Untitled](./UsingWrappedMatic/Untitled%203.png)

(B) Use the `Add to Metmask` to add the network to your Metamask and connecting the wallet; then you will have the ability to choose your wallet address or for that matter any wallet address can be entered:

![Untitled](./UsingWrappedMatic/Untitled%204.png)

(C) Change the amount to 100,000 and select `Get BB ETH` , you should get a confirmation, like this:

![Untitled](./UsingWrappedMatic/Untitled%205.png)

1. **Go to Wrapped Matic Contract**

(A) Go back to [home.buildbear.io](http://home.buildbear.io) and click the `Scan URL`

![Untitled](./UsingWrappedMatic/Untitled%206.png)

(B) Visit the Wrapped Matic Contract, in the Explorer: `0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270`

Your screen should be something similar to this:

![Untitled](./UsingWrappedMatic/Untitled%207.png)

(C) Go to the `Contract` tab and then `Write Contract` and `Connect to Web3:`

![Untitled](./UsingWrappedMatic/Untitled%208.png)

(D) Search for the `Deposit` function and enter the amount you would like, I did 50,000:

![Untitled](./UsingWrappedMatic/Untitled%209.png)

(E) Click `Write` ; Metamask should pop-up like this:

![Untitled](./UsingWrappedMatic/Untitled%2010.png)

*PS: In case the balance in Metamask is not updating, just change the network and come back to BuildBear network.  Metamask is not designed to read disposable test networks.  Refer here [Issues with Metamask | Now resolved](https://www.notion.so/Issues-with-Metamask-Now-resolved-c6326bd44b9549f58649fe3f3e0790a3)* 

(F) That is it, `confirm` and you will have the Wrapped Matic.  Go to the transaction hash to see your transaction:

![Untitled](./UsingWrappedMatic/Untitled%2011.png)

OPTIONAL: You can visit the `Advance` tab to see what happened in your transaction:

![Untitled](./UsingWrappedMatic/Untitled%2012.png)

You can similarly interact with any contract on the Polygon Mainnet and see what you can do in a transaction.

Next up: we will be doing some swap transactions on Uniswap, to show you more on the power of BuildBear.