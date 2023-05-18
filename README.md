
## Token Bound Accounts (TBAs)
Token bound accounts are smart wallets where the ownership of the wallet is tied to an ERC-721 token. 
Only the owner of the specified token can perform actions on the wallet such as sending or withdrawing tokens.

It can be thought of as a way of allowing ERC-721 tokens to hold other assets.

This template provides a way to programmatically deploy TBAs through the TokenBoundAccountFactory. Each TBA contract is ERC-4337 compliant and has the account abstraction infrastructure, such as paymasters, already set up and ready to use.

For more information on TBAs, read [this blog](https://blog.thirdweb.com/erc-6551-token-bound-accounts/).
### Pre Requisits
- This is a Foundry project so make sure that you have Foundry installed.
- Git.

### Getting Started

Firstly, clone this repo locally using `git clone`

These contracts extend the ERC-4337 compliant smart wallet `Account` and `BaseFactory` contracts provided by the thirdweb Solidity SDK in the `@thirdweb-dev/contracts` package.

To install the dependencies and make sure that Foundry is installed correctly run:

```bash
foundryup && forge clean && forge install
```

## Building the project

After any changes to the contract, run:

```bash
forge build
```

## Deploying Contracts Programatically 

Firstly, we will need to deploy our `TokenBoundAccountFactory` to be able to distribute TBAs to token holders. Run the following command to deploy your contract:

```bash
npx thirdweb deploy
```

Select the `TokenBoundAccountFactory` contract. This will pop up a browser window where you can select a chain and fill in the constructor parameters:

- `EntryPoint`: `0x5FF137D4b0FDCD49DcA30c7CF57E578a026d2789`

Now, deploy the `TokenBoundAccount` implementation contract in the same way, using the newly deployed factory contract address for the `factory` parameter.

Now, you can programatically create TBAs directly from the Dashboard from your factory contract OR you can build
your TBAs into a frontend using our [smart wallet connector](https://portal.thirdweb.com/wallet/smart-wallet#optional-properties).

## Join our Discord!

For any questions, suggestions, join our discord at [https://discord.gg/thirdweb](https://discord.gg/thirdweb).
