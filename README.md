# Arbitrage contracts

Execute flashloans for the betterment of UX and greater riches.

## Build

```
yarn
yarn build
```

## Test

We use Kovan to test the flashloan arbitrage.

First, prepare your `.env` file accordingly.

Deploy mock contracts:
```
yarn deploy-mocks
```

Update the contracts in `scripts/add-liquidity.ts`, if you want to
create the liquidity pools automatically and run the following command:
```
yarn add-liquidity
```

Finally, deploy the flashloan contract:
```
yarn deploy kovan scripts/deploy.ts
```


## Contracts

### USDC

Matic: https://polygonscan.com/address/0x2791bca1f2de4661ed88a30c99a7a9449aa84174
Mumbai: TODO

### Lending pool provider

Matic: https://polygonscan.com/address/0xd05e3E715d945B59290df0ae8eF85c1BdB684744
Mumbai: https://mumbai.polygonscan.com/address/0x178113104fEcbcD7fF8669a0150721e231F0FD4B

### Sushiswap router

Matic: https://polygonscan.com/address/0x1b02da8cb0d097eb8d57a175b88c7d8b47997506
Mumbai: TODO
