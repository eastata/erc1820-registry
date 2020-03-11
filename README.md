# ERC1820 Registry

A truffle project to deploy an ERC1820 Registry for Permissioned Chains.

## Install

    npm install -g truffle
    npm install

## Configuration

Edit truffle-config.js and add networks

## Deploy

    truffle migrate --network your-network

On deployment you will see the contract that it has been deployed to. Use this address to initialse the [Asset Token][1] contract deployment. 

[1]: https://github.com/clearmatics/asset-token
