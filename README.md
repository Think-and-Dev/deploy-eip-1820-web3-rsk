# Deploy EIP 1820

Ethereum [EIP 1820](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1820.md) is a standard for pseudo-introspection of smart contracts on Ethereum.

This library ensures that the EIP 1820 registry smart contract exists on any given chain.  Particularly useful for test environments.

Uses [web3.js v1.3.5](https://web3js.readthedocs.io/en/v1.3.5/).


# Setup

Install `@thinkanddev/deploy-eip-1820-web3-rsk` via yarn:

```sh
$ yarn add @thinkanddev/deploy-eip-1820-rsk
```

or npm:

```sh
$ npm i @thinkanddev/deploy-eip-1820-rsk
```

# Usage

To deploy EIP 1820 Registry contract on the network you are using

```javascript
const { deploy1820 } = require('@thinkanddev/deploy-eip-1820-web3-rsk')

async function deploy() {
    // The wallet must have at least 0.08 Ether
    const registryContract = await deploy1820(web3)

    // Now we have an Web3 Contract instance for the ERC1820 Registry contract
    let implementer = await registryContract.methods.getInterfaceImplementer('0x1234...', '0xINTERFACE_HASH').call()
}

```