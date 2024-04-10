# 🤹 LUKSO Playground

Convenient code snippets to interact with [LSP](https://docs.lukso.tech/standards/standards-roadmap) standards on LUKSO. Code examples are taken from the [LUKSO Tech Docs](https://docs.lukso.tech/) and are working as standalone scripts.

## Contents

- [`universal-profile`](./universal-profile): Universal Profile related scripts
- [`digital-assets`](./digital-assets/): Digital assets (LSP7/8) scripts
- [`interface-detection`](./interface-detection): Verify EIP165 Standard Compatibility
- [`key-manager`](./key-manager): Permission Management of Controller Keys
- [`metadata-detection`](./metadata-detection): Verify ERC725Y Storage Compatability
- [`transfer-lyx`](./transfer-lyx): Coin Transfers for Backend and Extension

### 📑 Smart contracts

- [`smart-contracts-hardhat`](./smart-contracts-hardhat): Hardhat Smart Contract Deployment Setup and Scripts

### LUKSO Libraries

- [`@erc725/erc725.js`](https://docs.lukso.tech/tools/erc725js/getting-started)
- [`@lukso/lsp-smart-contracts`](https://docs.lukso.tech/tools/lsp-smart-contracts/getting-started)

Please check the versions used in the [`package.json`](./package.json)

## Development

> A lot of these scripts should run with `ts-node` in development environnements, but you might be encountering issues because of ESM dependencies.

**This repository uses the [bun](https://bun.sh) toolkit to manage packages and run scripts.Make sure to [install it](https://bun.sh/docs/installation) first.**

Then clone this repository and install its dependencies.

```bash
git clone https://github.com/lukso-network/lukso-playground.git

cd lukso-playground && bun install
```

### Set the private environment variables

If you want to deploy something directly from your TS files, you will have to import a private key and profile address. You can simply copy the example environment files within the folders to access private data.

```bash
cp .env.example .env
```

> **INFO** Make sure to add the private key of an EOA for deployment. Optionally, you can provide a private key of a controller and a Universal Profile address to deploy contracts using your smart contract account.

### Run locally

Run the TypeScript code of one file within the terminal using `bun`.

```bash
bun file-path/script.ts
```

## IPFS Server

We highly recommend that developers fetch and store profile or asset data using **their own IPFS gateway** solutions like [Pinata](https://docs.pinata.cloud/docs/welcome-to-pinata) or [Infura](https://docs.infura.io/networks/ipfs). For development purposes, this repository uses the following RPC to fetch mainnet and testnet data:

- IPFS Gateway: `https://api.universalprofile.cloud/ipfs`

> LUKSO does not provide an official gateway for uploading asset data.
