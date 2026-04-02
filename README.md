# element-skills

A collection of OpenClaw skills for Element Market trading and market tracking.

This repository is designed for users who want to install these skills from ClawHub and use them in OpenClaw.

Copy the following prompt into OpenClaw to install both skills from ClawHub and check which environment variables still need to be configured.

```text
Install these two skills from ClawHub:
https://clawhub.ai/element-som/element-nft-trader
https://clawhub.ai/beelzebub520/element-nft-tracker

After installation, check which required environment variables are missing and tell me what I need to configure before using them.
```

## Available Skills

### Element NFT Trader

Trade NFTs on Element Market from OpenClaw.

ClawHub:
[https://clawhub.ai/element-som/element-nft-trader](https://clawhub.ai/element-som/element-nft-trader)

Supports:
- Create NFT listings
- Buy listed NFTs
- Place collection offers or token-specific offers
- Accept offers
- Cancel orders
- Query public collection orders
- Query account orders
- Get the configured trading wallet address

### Element NFT Tracker

Track Element Market collections, wallet activity, and market data from OpenClaw.

ClawHub:
[https://clawhub.ai/beelzebub520/element-nft-tracker](https://clawhub.ai/beelzebub520/element-nft-tracker)

Supports:
- Collection stats
- Ranking and trending collections
- Wallet NFT portfolio lookups
- Received offers
- Contract-to-slug resolution
- Recent wallet sales monitoring

## Install in OpenClaw

Install the skills directly from ClawHub using the links above.

After installation, configure the required environment variables in your OpenClaw environment.

### Required Environment Variables

#### `element-nft-trader`
- `ELEMENT_API_KEY`
- `ELEMENT_WALLET_PRIVATE_KEY`

#### `element-nft-tracker`
- `ELEMENT_API_KEY`

## Usage Overview

Use `element-nft-trader` for real trading actions and order management on Element Market.

Examples:
- "List this NFT for sale on Element"
- "Buy the cheapest listing from this collection"
- "Place a bid on this collection"
- "Cancel my current order"
- "Show my current account orders"
- "What is my configured trading wallet address?"

Use `element-nft-tracker` for read-only workflows focused on market data, wallet tracking, and monitoring.

Examples:
- "Show the floor price and 24h volume for this collection"
- "What NFTs does this wallet currently hold?"
- "Check the offers received on this wallet's NFTs"
- "Did this wallet sell any NFTs recently?"
- "Find the Element slug for this contract address"

## Example Prompts

### Trader examples
- "List token #1 from collection `0x...` for 0.1 ETH on Base"
- "Query current sell orders for collection `0x...` on Ethereum"
- "Place a collection offer on Base for 50 USDC"
- "Accept the best offer for token #12 on this collection"
- "Cancel my active order on BSC"

### Tracker examples
- "Show collection stats for this Element slug on Ethereum"
- "Show the top ranked collections on Base"
- "Check this wallet's NFT portfolio on BSC"
- "Did this wallet have any recent sales activity?"
- "Find the Element slug for this contract address"

## Notes on Behavior

### `element-nft-trader`
- This skill is designed for real order creation and execution.
- State-changing actions require explicit confirmation before execution.
- It uses a local private key for signing.
- It is intended for supported Element EVM networks.

### `element-nft-tracker`
- This skill is read-only.
- Wallet-related queries require explicit user consent before execution.
- It uses the Element API for collection and account-level data lookups.

## Important Safety Notes

- Never use your primary wallet for testing.
- Use a dedicated low-risk wallet for `element-nft-trader`.
- Never paste private keys into chat.
- Only provide `ELEMENT_WALLET_PRIVATE_KEY` through environment variables.
- Review the skill instructions and packaged runtime before using real funds.
- Treat all trading actions as live blockchain operations unless you have verified otherwise.

## Repository Structure

- `element-nft-trader/`: trading skill, references, TypeScript source, and prebuilt runtime
- `element-nft-tracker/`: read-only tracking skill

## Who This Repository Is For

This repository is for:
- OpenClaw users who want to install Element-related skills through ClawHub
- users who want trading and tracking separated into distinct skills
- users who want reusable skills instead of writing prompts from scratch each time
