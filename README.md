# element-skills

A collection of OpenClaw skills for Element Market trading and market tracking.

This repository is designed for users who want to install these skills from ClawHub and use them in OpenClaw.

## Quick Start

Copy the following prompt into OpenClaw. It will install both skills from ClawHub and then tell you which environment variables still need to be configured.

```text
Install these two skills from ClawHub:
https://clawhub.ai/element-som/element-nft-trader
https://clawhub.ai/beelzebub520/element-nft-tracker

After installation, check which required environment variables are missing and tell me what I need to configure before using them.
```

## Skills

### Element NFT Trader

ClawHub:
[https://clawhub.ai/element-som/element-nft-trader](https://clawhub.ai/element-som/element-nft-trader)

Use this skill for trading actions on Element Market.

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

ClawHub:
[https://clawhub.ai/beelzebub520/element-nft-tracker](https://clawhub.ai/beelzebub520/element-nft-tracker)

Use this skill for read-only Element Market data and wallet monitoring.

Supports:
- Collection stats
- Ranking and trending collections
- Wallet NFT portfolio lookups
- Received offers
- Contract-to-slug resolution
- Recent wallet sales monitoring

## Configuration

Set the required environment variables in OpenClaw after installation.

### `element-nft-trader`

- `ELEMENT_API_KEY`: your Element API key for querying Element Market APIs and submitting order-related requests. You can create or manage it here: [https://element.market/apikeys](https://element.market/apikeys)
- `ELEMENT_WALLET_PRIVATE_KEY`: the private key used locally to sign trading transactions and orders. Use a dedicated low-risk wallet instead of your primary wallet.

### `element-nft-tracker`

- `ELEMENT_API_KEY`: your Element API key for read-only Element Market queries. You can create or manage it here: [https://element.market/apikeys](https://element.market/apikeys)

## How To Use

Use `element-nft-trader` for real trading actions and order management.

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

### Trader

- "List token #1 from collection `0x...` for 0.1 ETH on Base"
- "Query current sell orders for collection `0x...` on Ethereum"
- "Place a collection offer on Base for 50 USDC"
- "Accept the best offer for token #12 on this collection"
- "Cancel my active order on BSC"

### Tracker

- "Show collection stats for this Element slug on Ethereum"
- "Show the top ranked collections on Base"
- "Check this wallet's NFT portfolio on BSC"
- "Did this wallet have any recent sales activity?"
- "Find the Element slug for this contract address"

## Behavior Notes

### `element-nft-trader`

- This skill is intended for real order creation and execution.
- State-changing actions require explicit confirmation before execution.
- The private key is used for local signing.
- This skill is intended for supported Element EVM networks.

### `element-nft-tracker`

- This skill is read-only.
- Wallet-related queries require explicit user consent before execution.
- It uses the Element API for collection and account-level data lookups.

## Safety Notes

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

- OpenClaw users who want to install Element-related skills through ClawHub
- Users who want trading and tracking separated into distinct skills
- Users who want reusable skills instead of writing prompts from scratch each time
