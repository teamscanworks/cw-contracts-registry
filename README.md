# CosmWasm Contracts Registry
This repository contains a `contracts.json` for a number of Cosmos-sdk chains with CosmWasm support. A `contracts.json` contains data that makes possible to verify wasm contract binaries and code-ids stored in a given chain against their source code. 

Smart contract verification is key to ensure users are running or executing the correct contract. We believe that an open-source, open-data repository should exist to democratize information access and improve the safety of the Cosmos ecosystem. For an introduction to smart contract verification, please visit the CosmWasm [docs](https://docs.cosmwasm.com/docs/1.0/smart-contracts/verify).

The CosmWasm Contracts Registry is heavily inspired by the Cosmos Chain Registry and aims to follow its structure and workflow. You can find more about the Cosmos Chain Registry in its github [repository](https://github.com/cosmos/chain-registry).

## Web Endpoints
- https://codes.scanworks.org/v1/

## APIs
- https://github.com/teamscanworks/codebreaker

## Web Interfaces
- TODO

## Contributing

We encourage pull requests from project teams to add contract data for a given chain `code-id` in the relevant `/{chain}/contracts.json`. We also accept pull requests from chain core developers to create their `chain` folder or update general chain data in the relevant `json` file.

# contracts.json

## Schema

A schema file containing the recommended metadata structure can be found at `contracts.schema.json` in the root directory. Schemas are still undergoing revision. Optional fields may be added beyond what is contained in the schema files.

## Sample

A sample `contracts.json` for a fictional `test` chain includes the following information:

```
{
    "$schema":"../contracts.schema.json",
    "chain_name":"test",
    "network_type":"mainnet",
    "pretty_name":"Test",
    "chain_id":"test-1",
    "bech32_prefix":"test",
    "codebase":{
       "git_repo":"https://github.com/test-labs/testchain",
       "cosmos_sdk_version":"0.45",
       "tendermint_version":"0.34",
       "cosmwasm_version":"0.24",
       "cosmwasm_enabled":true,
       "libwasm-version":"1.0.0"
    },
    "contracts":{
       "1":{
          "code_id":1,
          "verified": true,
          "checksum":"c369c36b686eee18159660b3e23466d95e7b1c700219a6b97d4383ffc800f1ad",
          "build_info":"workspace-optimizer:0.12.4",
          "build_env":"darwin/amd64",
          "module_name":"project1/dao-contract",
          "repository":"https://github.com/project1/dao-project",
          "release_tag":"https://github.com/project1/dao-project/releases/tag/v0.1.0",
          "org":"Project 1 Protocol"
       },
       "4":{
          "code_id":4,
          "verified": true,
          "checksum":"76c6c7bcac2f4214de478b530110295068789f73ed02a2d2599e2282f81f012a",
          "build_info":"workspace-optimizer:0.12.4",
          "build_env":"darwin/amd64",
          "module_name":"cw-plus/contracts/cw3-fixed-multisig/",
          "repository":"https://github.com/CosmWasm/cw-plus",
          "release_tag":"https://github.com/CosmWasm/cw-plus/releases/tag/v0.14.0",
          "org":"cw-plus-maintainer",
          "security_contact": "https://github.com/CosmWasm/cw-plus/blob/main/SECURITY.md"
       }
    }
 }
 ```
