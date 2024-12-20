# Glow Swap

An efficient and user-friendly DEX natively built on B² network.


## Contracts

- There are three main contracts, Factory Contract, Pool contract and Router contract.

## DATA AND CONTROL FLOWS

- Trader/liquidity provider interacts with Router contract not with main pool contract directly

## Swap

### Caller

1. Approve periphery contract to use trader's tokens
2. Trader uses router contract to swap tokens

### In the Router contract

3. Sends tokenA to core contract
4. Calculates tokenOut
5. Then iterate over path array and swap tokens untill desired token come

### In the Pool contract

6. Then we sends the token to trader
7. Update the reserves

## Add Liquidity

### Caller

1. Approve periphery contract to use liquidity provider's tokens
2. Liquidity provider uses router contract to add liquidity

### In the Router contract

3. Sends assets of liquidity provider to core contract

### In the Pool contract

3. Calculate liquidity tokens to be minted
4. Mint liquidity tokens for liquidity provider
5. Update the reserves

## Remove Liquidity

### Caller

1. Approve periphery contract to use liquidity provider's tokens
2. Liquidity provider uses router contract to withdraw liquidity

### In the Router contract

3. Sends liquidity tokens of liquidity provider to core contract

### In the Pool contract

4. Burn liquidity tokens
5. Send assets back to liquidity provider
6. Update the reserves
