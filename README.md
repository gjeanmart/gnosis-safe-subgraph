
# Safe subgraph

This Subgraph dynamically tracks activity on any Safe{Wallet} deployed through the factory (current support for versions 1.1.1, 1.3.0, 1.4.0 and 1.4.1)

### Subgraphs

All networks which are supported by Eternal Safe and The Graph network are supported by this subgraph.

- Mainnet: TODO
- Gnosis Chain: TODO
- Polygon: TODO
- BNB Chain: TODO
- Arbitrum: TODO
- Optimism: TODO
- Base: TODO
- Celo: TODO
- Avalanche: TODO

As of writing, the following networks are not supported by the [decentralized network](https://thegraph.com/docs/en/developing/supported-networks/):
- Polygon zkEVM
- zkSync Era
- Aurora
- Sepolia

## Prerequiste

- yarn
- graph-cli

```
$ yarn global add @graphprotocol/graph-cli
```

## Getting started

Install the dependencies

```
$ yarn install
```

Build

```
$ ./script/build.sh [--reset] [--code-gen] [--network mainnet|ropsten|kovan|goerli|mumbai|polygon]
```

- `--reset -r` deletes the build and generated code folders [optional, default: false]
- `--code-gen -c` (re)generate code from schema [optional, default: false]
- `--network -n` select a target network (mainnet, ropsten, kovan, goerli, mumbai, polygon) [optional, default: mainnet]


## Deployment

```
$ ./script/deploy.sh [--network mainnet|ropsten|kovan|goerli|mumbai|polygon] [--local] [--access-token xxxxxxxxxxxx] [--product studio]
```

- `--network -n` select a target network (mainnet, ropsten, kovan, goerli, mumbai, polygon) [optional, default: mainnet]
- `--access-token -t` access token to deploy the subgraph [optional, default: env variable $THEGRAPH_ACCESS_TOKEN]
- `--product -p` select a target TheGraph product (studio, hosted-service) [optional, default: studio]


## Model

- Wallet
    -  Transaction

## Query samples

### Get Wallet details 

```graphql
{
  wallet(id: "0x12312312.....") {
    id
    version
    creator
    network
    stamp
    hash
    factory
    mastercopy
    version
    owners
    threshold
    currentNonce
    transactions {
      id
      stamp
      hash
      status
      value
      destination
      data
      signatures
      nonce
      operation
      estimatedSafeTxGas
      estimatedBaseGas
      estimatedGasPrice
      gasToken
      refundReceiver
      gasUsed
      gasPrice
    }
  }
}

```

