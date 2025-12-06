# Getting Started

This guide will help you set up your development environment to work with Purple Squirrel Media projects.

---

## Prerequisites

### Required Software

| Software | Version | Purpose |
|----------|---------|---------|
| **Node.js** | <= 16.x | Runtime (v17+ not supported) |
| **Yarn** | Latest | Package manager |
| **Git** | Latest | Version control |
| **Rust** | Latest stable | For Solana programs |
| **Solana CLI** | Latest | Blockchain interaction |

### Recommended Tools
- **VS Code** - Code editor with Solana extensions
- **Phantom Wallet** - Browser wallet for testing
- **Docker** - For containerized development

---

## Installation Steps

### 1. Install Node.js

```bash
# Using nvm (recommended)
nvm install 16
nvm use 16

# Verify installation
node --version  # Should show v16.x.x
```

### 2. Install Yarn

```bash
npm install -g yarn
yarn --version
```

### 3. Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source ~/.cargo/env
rustc --version
```

### 4. Install Solana CLI

```bash
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
export PATH="$HOME/.local/share/solana/install/active_release/bin:$PATH"
solana --version
```

### 5. Configure Solana

```bash
# Set to devnet for development
solana config set --url devnet

# Create a new wallet for development
solana-keygen new

# Airdrop some SOL for testing
solana airdrop 2
```

### 6. Install Metaplex CLI (for NFT projects)

Follow the instructions at [Metaplex CLI Installation](https://docs.metaplex.com/tools/sugar/installation).

---

## Project Setup

### Clone a Repository

```bash
# Example: Clone the candymachine project
git clone https://github.com/PurpleSquirrelMedia/candymachine.git
cd candymachine
```

### Install Dependencies

```bash
yarn install
```

### Configure Environment

```bash
# Copy example environment file
cp .env.example .env

# Edit with your settings
nano .env  # or use your preferred editor
```

### Start Development Server

```bash
yarn start
```

---

## Common Environment Variables

Most Purple Squirrel Media projects use these environment variables:

```env
# Solana Network Configuration
REACT_APP_SOLANA_NETWORK=devnet
REACT_APP_SOLANA_RPC_HOST=https://api.devnet.solana.com

# Candy Machine (for NFT projects)
REACT_APP_CANDY_MACHINE_ID=your_candy_machine_pubkey

# SPL Token (optional)
REACT_APP_SPL_TOKEN_TO_MINT_NAME=PURP
REACT_APP_SPL_TOKEN_TO_MINT_DECIMALS=9
```

---

## Network Configuration

### Devnet (Development)
```bash
solana config set --url devnet
# RPC: https://api.devnet.solana.com
```

### Testnet (Testing)
```bash
solana config set --url testnet
# RPC: https://api.testnet.solana.com
```

### Mainnet-Beta (Production)
```bash
solana config set --url mainnet-beta
# RPC: https://api.mainnet-beta.solana.com
```

> **Note**: For production, consider using a dedicated RPC provider like QuickNode, Alchemy, or Helius for better reliability.

---

## Wallet Setup

### Phantom Wallet (Recommended)

1. Install [Phantom](https://phantom.app/) browser extension
2. Create a new wallet or import existing
3. Switch to the appropriate network (Devnet for testing)
4. Get devnet SOL from a [faucet](https://solfaucet.com/)

### Sollet Wallet

1. Visit [sollet.io](https://sollet.io/)
2. Create a new wallet
3. Note your seed phrase securely

### CLI Wallet

```bash
# Create new wallet
solana-keygen new --outfile ~/.config/solana/devnet.json

# Set as default
solana config set --keypair ~/.config/solana/devnet.json

# Get public key
solana address
```

---

## Development Workflow

### 1. Create a Branch

```bash
git checkout -b feature/your-feature-name
```

### 2. Make Changes

Edit files as needed for your feature or fix.

### 3. Test Locally

```bash
# Run development server
yarn start

# Run tests (if available)
yarn test
```

### 4. Build for Production

```bash
yarn build
```

### 5. Submit PR

```bash
git add .
git commit -m "Description of changes"
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub.

---

## Troubleshooting

### Common Issues

#### Node.js Version Error
```
Error: Node version 17 is not supported
```
**Solution**: Use Node.js version 16 or lower
```bash
nvm use 16
```

#### Insufficient SOL
```
Error: Insufficient funds
```
**Solution**: Airdrop more SOL
```bash
solana airdrop 2
```

#### RPC Rate Limiting
```
Error: 429 Too Many Requests
```
**Solution**: Use a dedicated RPC provider or add delays between requests

#### Build Failures
```bash
# Clear cache and reinstall
rm -rf node_modules yarn.lock
yarn install
```

---

## Useful Commands

```bash
# Check Solana configuration
solana config get

# Check wallet balance
solana balance

# View recent transactions
solana transaction-history

# Get cluster version
solana cluster-version

# View program logs
solana logs
```

---

## Next Steps

- Read the [Project Categories](Project-Categories) to find projects to work on
- Check [Contributing](Contributing) guidelines
- Explore the [NFT & Marketplaces](NFT-and-Marketplaces) documentation

---

[Back to Home](Home)
