# NFT & Marketplaces

Complete documentation for Purple Squirrel Media's NFT infrastructure and marketplace solutions.

---

## Overview

Purple Squirrel Media provides a comprehensive suite of NFT tools built on **Solana** using the **Metaplex** protocol. Our solutions cover the entire NFT lifecycle from minting to secondary market trading.

## Candy Machine

### Repository
[`candymachine`](https://github.com/PurpleSquirrelMedia/candymachine)

### Description
Production-ready Candy Machine V2 responsive UI that can be customized in minutes. All Candy Machine V2 functionalities are implemented, auto-detected, and maintained up-to-date.

### Supported Features

| Feature | Description |
|---------|-------------|
| **Public Mint** | With countdown when date is in the future |
| **Civic Support** | Gatekeeper integration for identity verification |
| **Whitelist** | Whitelist-only minting phases |
| **Presale** | true/false presale configuration |
| **End Settings** | End date or end number (endSettings) |
| **SPL Token Mint** | Custom SPL token for payment |
| **Multi-Mint** | Multiple mints in single transaction |

### Supported Wallets
- Phantom
- Solflare
- Sollet
- Slope
- Torus
- Ledger

### Quick Start

#### Prerequisites
- Node.js version <= 16 (version 17 not supported)
- Yarn package manager
- Solana CLI tools
- Metaplex CLI

#### Installation

```bash
# Clone the repository
git clone https://github.com/PurpleSquirrelMedia/candymachine.git
cd candymachine

# Install dependencies
yarn install

# Configure environment
cp .env.example .env
# Edit .env with your settings
```

#### Environment Variables

```env
# Your Candy Machine public key
REACT_APP_CANDY_MACHINE_ID=__YOUR_CANDY_MACHINE_ID__

# Network: devnet, testnet, or mainnet-beta
REACT_APP_SOLANA_NETWORK=devnet

# RPC endpoint
REACT_APP_SOLANA_RPC_HOST=https://api.devnet.solana.com

# (Optional) SPL Token settings
REACT_APP_SPL_TOKEN_TO_MINT_NAME=
REACT_APP_SPL_TOKEN_TO_MINT_DECIMALS=9
```

#### Development

```bash
# Start development server
yarn start

# Build for production
yarn build
```

#### Customization

1. **Colors** - Update CSS variables in `App.css`:
```css
:root {
  --main-background-color: #343A50;
  --card-background-color: #804980;
  --countdown-background-color: #433765;
  --main-text-color: #F7F6F4;
  --title-text-color: #3CBA8B;
}
```

2. **Images** - Replace files in `public/` folder
3. **Content** - Edit `Home.tsx` starting at line 380

### One-Click Deployment

Deploy to Vercel with one click:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FPurpleSquirrelMedia%2Fcandymachine)

---

## Metaplex Integration

### Repository
[`Metaplex`](https://github.com/PurpleSquirrelMedia/Metaplex)

### Description
Full implementation of the Metaplex protocol for creating, minting, and auctioning NFTs on Solana.

### NFT Types

#### Master Edition
- Represents both an NFT and metadata for print control
- Creator can distribute print rights
- Can set max supply
- Remains in artist's wallet while prints are sold

#### Print
- Copy of an NFT created from Master Edition
- Each has a unique edition number
- Created during auctions or manually

#### Normal NFT
- One-of-a-kind artwork
- No print rights
- Transfers fully to purchaser

### Auction Types

| Type | Description |
|------|-------------|
| **Single Item** | Sell normal NFTs, prints, or Master Editions |
| **Open Edition** | Unlimited prints, all bidders receive one |
| **Limited Edition** | Fixed number of prints as prizes |
| **Tiered Auction** | Mix of different prize types |

### Royalties
- On-chain artist splits for collaborations
- Automatic royalty payments on resales
- Configurable percentages per collaborator

### Installation

```bash
git clone https://github.com/PurpleSquirrelMedia/Metaplex.git
cd Metaplex/js
yarn install && yarn bootstrap && yarn build
yarn start
```

Navigate to `http://localhost:3000/`

---

## Treats Marketplace

### Repository
[`treats-marketplace`](https://github.com/PurpleSquirrelMedia/treats-marketplace)

### Description
Complete NFT marketplace solution combining Candy Machine V2 primary sales with Candy Shop secondary marketplace.

### Features
- Primary sales through Candy Machine V2
- Secondary marketplace with Candy Shop integration
- Responsive design
- One-click Vercel deployment

### Quick Start

```bash
git clone https://github.com/PurpleSquirrelMedia/treats-marketplace.git
cd treats-marketplace
yarn install
cp .env.example .env
# Configure your environment
yarn start
```

---

## Candy Shop V2

### Repository
[`candy-shop-v2`](https://github.com/PurpleSquirrelMedia/candy-shop-v2)

### Description
Advanced secondary marketplace implementation using Candy Shop V2.

---

## NFT Gallery

### Repository
[`solana-nft-gallery`](https://github.com/PurpleSquirrelMedia/solana-nft-gallery)

### Description
Showcase application for displaying NFT collections on Solana.

---

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    User Interface                        │
│  (React/TypeScript - candymachine, treats-marketplace)  │
└─────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────┐
│                   Metaplex Protocol                      │
│        (NFT Standard, Auctions, Storefronts)            │
└─────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────┐
│                   Solana Blockchain                      │
│              (SPL Tokens, Programs, PDAs)               │
└─────────────────────────────────────────────────────────┘
```

---

## Best Practices

1. **Always test on devnet first** before deploying to mainnet
2. **Secure your wallet** - never expose private keys
3. **Verify candy machine configuration** before going live
4. **Set appropriate royalties** for long-term revenue
5. **Use whitelists** for fair launches

---

## Resources

- [Metaplex Documentation](https://docs.metaplex.com/)
- [Solana Documentation](https://docs.solana.com/)
- [Candy Machine V2 Guide](https://docs.metaplex.com/candy-machine-v2/Introduction)

---

[Back to Home](Home) | [Project Categories](Project-Categories)
