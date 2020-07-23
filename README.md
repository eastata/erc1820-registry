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

## Deploy using Docker

* **Ganache** network
  * Run Ganache network
    ```
    docker run -d -p 8545:8545 --name ganache trufflesuite/ganache-cli:v6.9.1 --gasLimit 0xFFFFFFFF
    ```
  * Deploy ERC1820 Registry contract
    ```
    docker run --network="host" -t clearmatics/erc1820-registry
    ```

* **Autonity** or other networks with custom settings
  * Create custom [./truffle-config.js](https://www.trufflesuite.com/docs/truffle/reference/configuration) file in local dir.
  Deployment will use network `development`
  * Deploy ERC1820 Registry contract
    ```
    docker run -v "$(pwd)"/truffle-config.js:/app/truffle-config.js --network="host" -t \
    clearmatics/erc1820-registry \
    deploy -- --f 2 --describe-json
    ```
    Any options for [truffle migrate](https://www.trufflesuite.com/docs/truffle/reference/truffle-commands#migrate) could be used
  


[1]: https://github.com/clearmatics/asset-token
