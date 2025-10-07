# AMM Smart Contracts

This project contains the smart contracts for an Automated Market Maker (AMM) on the Stacks blockchain, written in Clarity.

## Contracts

### `contracts/amm.clar`

This is the core AMM contract that facilitates decentralized token swaps.

#### Features
- **Create Pools:** Anyone can create a liquidity pool for a pair of SIP-010 tokens.
- **Provide Liquidity:** Users can deposit an equal value of two tokens into a pool to become liquidity providers and earn fees.
- **Swap Tokens:** Users can trade one token for another through the liquidity pools. The contract uses a constant product formula (`x * y = k`) to determine prices.
- **Fees:** A small fee is taken from each swap and added to the pool's liquidity, rewarding liquidity providers.

#### Key Public Functions
- `create-pool`: Establishes a new liquidity pool for a pair of tokens with a specific fee tier.
- `add-liquidity`: Allows users to add liquidity to a pool and receive LP tokens in return.
- `remove-liquidity`: Allows users to burn their LP tokens to withdraw their proportional share of the pool's assets.
- `swap`: Executes a trade between two tokens in a pool.

### `contracts/mock-token.clar`

This is a simple implementation of a SIP-010 fungible token used for testing and development. It allows for minting and transferring tokens to simulate a real-world environment for the AMM.

#### Features
- Implements the `sip-010-trait-ft-standard`.
- `mint`: Creates new tokens and distributes them to a specified principal.
- Standard token functions like `transfer`, `get-balance`, `get-total-supply`, etc.
