# Swappland Market Contract Open-RPC Specification and Client

## What is Swappland? 
[Swappland](https://swapp.land) is a p2p Marketplace for Near, where people can trade NFT for NFT or Near for NFT, and eventually all forms of tokens for an NFT. We allow anyone to list any in their wallet for trade. This is the dev friendly client. 

The specification here is the Open-RPC[openrpc] specification of the client.

## Usage

### Installation 
```
npm install @swappland/market-contract-client
```

```ts
import SwapplandClient from "@swappland/market-contract-client"

const testnetContractId ="mkt.landofswapps.testnet"
const mainnetContractid = "mkt.swappland.near"

// Setup Purely for example
const accountId: string = "some_account_you_have_in_credentials.near"
const keystore = new keyStores.UnencryptedFileSystemKeyStore(`${os.homedir()}/.near-credentials`)
const near = new Near({
    networkId: "testnet",
    nodeUrl: "https://rpc.testnet.near.org",
    walletUrl: "https://wallet.testnet.near.org",
    explorerUrl: "https://explorer.testnet.near.org", 
    deps: {keyStore}, headers:{}})

// The only thing the client really needs  followed by the contractId
const account:Account = await near.account(accountId);

const client = new SwapplandClient({account, contractId: testnetContractId})

client.

```

### Build 
```
npm install
npm run build
```

### Early days note.
It's early days and the interface is still subject to change depending on usecases that come up. 
A few methods still need to be deprecated around the adminstration of the contract here's a that was 
easy link to the [spec][market-spec](beware some non essential methods are now deprecated, but are pending removal from spec).


## Contributing

The specification is written in [OpenRPC][openrpc] uses the [Open-Rpc Near Client Generator](generator) and the [Open RPC Near Token Standards](https://github.com/swappland/open-rpc-near-token-standards). Refer to the
OpenRPC specification and the JSON schema specification to get started.


[generator]: https://github.com/shipsgold/open-rpc-near-client-generator
[market-spec]: https://playground.open-rpc.org/?schemaUrl=https://raw.githubusercontent.com/swappland/swappland-market-contract-spec/main/build/openrpc.json&uiSchema[appBar][ui:splitView]=false&uiSchema[appBar][ui:input]=false&uiSchema[appBar][ui:examplesDropdown]=false
[openrpc]: https://open-rpc.org

