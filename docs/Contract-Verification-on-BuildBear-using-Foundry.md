---
sidebar_position: 4
---
# Contract Verification on BuildBear using Foundry

To deploy and verify contracts on your sandbox through Foundry, follow the instructions below:

NOTE: All the necessary code snippets are available on your BuildBear dashboard. Simply copy and paste them.

Important Note: Foundry currently supports script-based verification exclusively for Public Chains, i.e., for chains whose Chain IDs it recognizes. As a result, the verification process varies for our premium and free users.

## For Premium Users 

### Step 1: Add BuildBear to your Foundry.toml file


```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
[rpc_endpoints]
buildbear = "https://rpc.buildbear.io/Sandbox_ID"
[etherscan]
buildbear = { key = "verifyContract", url="https://rpc.buildbear.io/verify/etherscan/Sandbox_ID" }
```

### Step 2:  To deploy and verify contracts using scripts, employ the following command:

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
forge script script/<SCRIPT_NAME>.s.sol --rpc-url buildbear --private-key "<PRIVATE_KEY_OF_UNLOCKED_ACCOUNTS>"  --etherscan-api-key "verifyContract" --verifier-url "https://rpc.buildbear.io/verify/etherscan/Sandbox_ID" -vvvv --broadcast --verify --slow
```

### Step 3:  To streamline the process for future deployments, add the following Justfile to your Foundry root directory:
*Please note that Justfiles are currently supported only on Mac, Linux, and WSL.*

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
run-script script_name flags='' sig='' args='':
  sh -c 'FOUNDRY_PROFILE=ci forge script script/{{script_name}}.s.sol {{sig}} {{args}} \
    --rpc-url "https://rpc.buildbear.io/Sandbox_ID" \
    --private-key "<PRIVATE_KEY_OF_UNLOCKED_ACCOUNTS>" \
    --etherscan-api-key "verifyContract" \
    --verifier-url "https://rpc.buildbear.io/verify/etherscan/Sandbox_ID" \
    -vvvv {{flags}}' 

deploy-verify:
  sh -c 'just run-script "<SCRIPT_NAME>" "--broadcast --verify --slow"'
```
To execute the justfile to deploy/verify contracts, use the following command:

```json
just deploy-verify
```
## For Free Users 
Important Note: *Foundry currently supports script-based verification exclusively for Public Chains, i.e, for Chains whose Chain IDs it recognises. Thus, this process is practically only useful if you have deployed 1 or 2 contracts:*

### Step 1: Add BuildBear to your Foundry.toml file

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
[rpc_endpoints]
buildbear = "https://rpc.buildbear.io/Sandbox_ID"
[etherscan]
buildbear = { key = "verifyContract", url="https://rpc.buildbear.io/verify/etherscan/Sandbox_ID" }
```

### To verify the deployed contracts, execute the following command:

```json
// CUSTOMIZED CODE SNIPPET AVAILABLE IN YOUR DASHBOARD
forge verify-contract --constructor-args "" --etherscan-api-key "verifyContract" --verifier-url "https://rpc.buildbear.io/verify/etherscan/Sandbox_ID" {DEPLOYED_CONTRACT_ADDRESS} {Path}/{Contract_Name}.sol:{Contract_Name}
```
*Alternative route:*

Upgrade to a premium account to align your Sandbox with Mainnet's chain ID. This allows you to utilize script-based verification and access advanced features, including:

### Premium Features

1. **Static RPC:** All Sandboxes created by BuildBear have a unique RPC. For our premium clients, a static RPC is allocated to their Sandboxes consistently. This aids in configuring hardhat, Foundry, and project files.
2. **Extended Sandbox Life:** Currently, any sandbox created by free users that remains unused for a period of 4 days is pruned by our system. However, for premium users, their sandboxes will not be pruned and will enjoy an extended lifespan.
3. **Third-party Integrations:**
Enhance your sandbox by integrating additional services like Gelato for automated smart contract execution, Gnosis Safe for a secure smart contract wallet, Chainlink for decentralized token price feeds, and more.
4. **Scalability:**
Initially, BuildBear sandboxes start at a very basic level. However, as the workload on the sandbox grows due to testing or application expansion, the sandbox resources autonomously adjust to meet your usage requirements and accommodate growth.
5. **Sandbox Chain ID:**
Currently, sandboxes created by free users receive a chain ID that is different from the Mainnet they were forked from. However, for premium users, their sandboxes have the same chain ID as the Mainnet they were forked from.

#### For further discussions and details, feel free to reach out to us at [team@buildbear.io](mailto:team@buildbear.io) or through our Chat Bot.