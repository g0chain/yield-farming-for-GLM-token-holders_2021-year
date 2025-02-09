# GLM Stake Pool

***
## Introduction of GLM Stake Pool
- This is a smart contract in order to provide the opportunity of yield farming for Golem's GLM token holders (by staking uniswap-LP tokens that is a pair between GLM and ETH into the stake pool).

&nbsp;

***

## Workflow
1. Create UniswapV2-Pool between GLM token and ETH. (Add Liquidity)
2. Create UNI-V2 LP tokens (GLM-ETH).
3. Stake UNI-V2 LP tokens (GLM-ETH) into the GLM stake pool contract.
4. Smart contract (the GLM stake pool contract) automatically generate rewards every week.
  - The `Golem Governance Token (GGC)` is generated as rewards. 
  - Current formula of generating rewards is that:
    - 10% of staked UNI-V2 LP tokens (GLM-ETH) amount in a week is generated each week. 
    - Staker can receive rewards ( `Golem Governance Token` ) depends on their `share of pool` when they claim rewards.
5. Claim rewards and distributes rewards into claimed-staker (or, Un-Stake UNI-V2 LP tokens. At that time, claiming rewards will be executed at the same time).

&nbsp;

***

## Technical Stack
- Solidity (Solc): v0.5.16
- Truffle: v5.1.60
- web3.js: v1.2.9
- Node.js: v11.15.0
- Libraries
  - @openzeppelin/contracts: v2.5.1 etc...
&nbsp;

***

## Setup
### 1. Install modules
```
$ npm install
```

<br>

### 2. Add `.env` to the root directory. 
- Please reference `.env.example` to create `.env` 


<br>

### 3. Compile & migrate contracts (on Rinkeby testnet)
```
$ npm run migrate:local
```

<br>

### 4. Test (Mainnet-fork approach with Ganache-CLI)
```
$ ganache-cli --fork https://mainnet.infura.io/v3/{YOUR INFURA KEY}
```

Then,  

- All of tests
```
$ npm run test
```

- Only test of the Stake Pool contract
```
$ npm run test:stake
```

&nbsp;

***

## Remaining tasks and next steps
- Replace GLMMockToken contract (GLMMockToken.sol) with official GLM token contract (NewGolemNetworkToken.sol).
- Additional implementation of GLM stake pool between GLM-ERC20.
- Additional implementation of the Golem Governance Token (GGC) and governance structures (e.g. Community voting function by GLM token holders)
- Add liquidity pool of the Golem Governance Token (GGC).
- Implement the front-end (UI).