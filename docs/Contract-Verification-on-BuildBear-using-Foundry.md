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
## For Non-Premium Users 
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

1. **Static RPC:** Get a dedicated RPC for your BuildBear sandboxes, making it easier to configure hardhat, Foundry, and project files.

2. **Extended Sandbox Life:** Your BuildBear sandboxes won't be deleted if they're inactive for a while, giving you more flexibility.

3. **Enhanced Integrations:** Integrate with popular services like Gelato, Gnosis Safe, and Chainlink to expand your sandbox's capabilities.

4. **Automatic Scalability:** Your BuildBear sandbox resources will automatically adjust to meet your usage demands, ensuring smooth operation.

5. **Matching Chain ID:** Your BuildBear sandbox will have the same Chain ID as the Mainnet it's forked from, simplifying development.



#### For further discussions and details, feel free to reach out to us at [team@buildbear.io](mailto:team@buildbear.io) or through our Chat Bot.