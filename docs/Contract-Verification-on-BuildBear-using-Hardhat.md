---
sidebar_position: 3
---
# Contract Verification on BuildBear using Hardhat

Following are the instructions for you to update your `hardhat.config.js` or `hardhat.config.ts` file to be able to deploy and verify your smart contracts programmatically.  

NOTE: All the necessary code snippets that you will need for your hardhat.config file is available for you in your BuildBear dashboard. You just have to copy and paste them. As shown below.

![Untitled](./images/Home-BuildBear%20(7).png)

## Step 1: Add BuildBear to your Networks

Add a new object `buildbear` in the `networks` object in your `hardhat.config.js` or `hardhat.config.ts`; similar to the following:

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
networks: {
  buildbear: {
    url: "https://rpc.buildbear.io/Sandbox_ID",  
		accounts: ["Add Private Key Here"],
  }
}
```

## Step 2: Add a Custom Chain to the Etherscan Object

Add a new object `customChain` in the `etherscan` similar to the following:

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
etherscan: {
	apiKey: {
		buildbear: "verifyContrats"
	}
  customChains: [
    {
      network: "buildbear",
      chainId: 8120,
			// Insert the ChainId received from BuildBear Dashboard
      urls: {
        apiURL:"https://rpc.buildbear.io/verify/etherscan/Sandbox_ID",
        browserURL: "https://explorer.buildbear.io/node/Sandbox_ID",
      },
    },
  ],
}
```

That is it.  Once the above is done, run your scripts to deploy and verify your smart contracts programmatically on BuildBear.



## If you are facing any issues with BuildBear, feel free to report them to us at **[team@buildbear.io](mailto:team@buildbear.io)**