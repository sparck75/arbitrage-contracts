# Arbitrage contracts

Utilize flashloans to arbitrage Uniswap v2 AMMs.

## Build

```
yarn
yarn build
```

## Test

Kovan is used to test the flashloan arbitrage.

First, prepare your `.env` file accordingly. No stablecoin token is
deployed below, for that you will need to use the
[AAVE faucet](https://staging.aave.com/#/faucet), otherwise we won't
be able to execute flashloans if the borrowed asset is not whitelisted
in AAVE.

Deploy mock contracts:
```
yarn deploy-mocks
```

Update the contracts in `scripts/add-liquidity.ts`, if you want to
create the liquidity pools automatically, and run the following command:
```
yarn add-liquidity
```

Finally, deploy the flashloan contract:
```
yarn deploy kovan scripts/deploy.ts
```

Now, you can submit a flashloan request with a path that includes an
arbitrage and it should be successfully executed by the contract. An
example client of this contract can be found [here](https://github.com/kargakis/arbitragoor).

## Contracts

| Contract              | Matic                                                                                                                    | Kovan                                                                                                                       |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------|------------|
| USDC                  | [0x2791bca1f2de4661ed88a30c99a7a9449aa84174](https://polygonscan.com/address/0x2791bca1f2de4661ed88a30c99a7a9449aa84174) | Check [AAVE faucet](https://staging.aave.com/#/faucet)                                                                                         |
| Lending pool provider | [0xd05e3E715d945B59290df0ae8eF85c1BdB684744](https://polygonscan.com/address/0xd05e3E715d945B59290df0ae8eF85c1BdB684744) | [0x88757f2f99175387aB4C6a4b3067c77A695b0349](https://kovan.etherscan.io/address/0x88757f2f99175387aB4C6a4b3067c77A695b0349) |
| Liquidity router #0   | [0x1b02da8cb0d097eb8d57a175b88c7d8b47997506](https://polygonscan.com/address/0x1b02da8cb0d097eb8d57a175b88c7d8b47997506) | [0x1b02dA8Cb0d097eB8D57A175b88c7D8b47997506](https://kovan.etherscan.io/address/0x1b02dA8Cb0d097eB8D57A175b88c7D8b47997506) |
| Liquidity router #1   | [0xa5E0829CaCEd8fFDD4De3c43696c57F7D7A678ff](https://polygonscan.com/address/0xa5E0829CaCEd8fFDD4De3c43696c57F7D7A678ff) | [0x7a250d5630B4cF539739dF2C5dAcb4c659F2488D](https://kovan.etherscan.io/address/0x7a250d5630B4cF539739dF2C5dAcb4c659F2488D) |
