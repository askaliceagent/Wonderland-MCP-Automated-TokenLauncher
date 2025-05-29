# 🎪 Wonderland MCP Documentation

Welcome to Wonderland MCP - Your magical gateway to Solana meme token creation and trading! This documentation will guide you through everything you need to know about using the Wonderland MCP server.

## Table of Contents

- [Introduction](#introduction)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Configuration](#configuration)
- [Features](#features)
- [API Reference](#api-reference)
- [Integration Guides](#integration-guides)
- [Examples & Tutorials](#examples--tutorials)
- [Troubleshooting](#troubleshooting)
- [Security Best Practices](#security-best-practices)
- [FAQ](#faq)

---

## 🌟 Introduction

### What is Wonderland MCP?

Wonderland MCP is a powerful Model Context Protocol (MCP) server that enables seamless interaction with Pump.fun tokens on the Solana blockchain. Built for creators, traders, and meme enthusiasts, it provides a comprehensive suite of tools for token management, trading, and market analysis.

### Key Features at a Glance

- 🚀 **Token Creation**: Launch your meme token in minutes
- 💰 **Trading**: Buy and sell tokens directly through the bonding curve
- 📊 **Market Data**: Real-time trending tokens and new listings
- 🎨 **AI Image Generation**: Create professional token logos with OpenAI
- 👛 **Wallet Management**: Multi-wallet support with balance tracking
- 🔍 **Advanced Search**: Find tokens by name, symbol, or address

### Why Choose Wonderland MCP?

- **User-Friendly**: Natural language interface through Claude Desktop
- **Secure**: Your private keys never leave your local environment
- **Fast**: Direct integration with Helius RPC for lightning-fast transactions
- **Comprehensive**: All-in-one solution for meme token operations

---

## 🚀 Quick Start

Get up and running with Wonderland MCP in under 5 minutes!

### Prerequisites

- Node.js (v18+) or Bun runtime
- Claude Desktop with MCP support enabled
- A Solana wallet with some SOL for transactions

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/wonderland-mcp.git
cd wonderland-mcp

# Install dependencies
bun install

# Copy environment template
cp .env.example .env

# Edit .env with your API keys
nano .env

# Build and start
bun run build
bun run start
```

### Your First Token

Once connected to Claude Desktop, try:

> "Create a new token called 'Wonder Coin' with symbol 'WNDR' and generate a magical logo for it"

---

## 💻 Installation

### System Requirements

- **Operating System**: macOS, Linux, or Windows (with WSL)
- **Node.js**: Version 18.0.0 or higher
- **Memory**: At least 4GB RAM recommended
- **Storage**: 500MB free space

### Step-by-Step Installation

#### 1. Install Dependencies

First, ensure you have Node.js installed:

```bash
node --version  # Should output v18.0.0 or higher
```

Or install Bun (recommended for better performance):

```bash
curl -fsSL https://bun.sh/install | bash
```

#### 2. Clone the Repository

```bash
git clone https://github.com/yourusername/wonderland-mcp.git
cd wonderland-mcp
```

#### 3. Install Node Packages

Using npm:
```bash
npm install
```

Using Bun:
```bash
bun install
```

#### 4. Build the Project

```bash
bun run build
# or
npm run build
```

#### 5. Configure Claude Desktop

Add the following to your Claude Desktop MCP configuration file:

```json
{
  "mcpServers": {
    "wonderland": {
      "command": "node",
      "args": ["/path/to/wonderland-mcp/build/index.js"],
      "env": {
        "HELIUS_API_KEY": "your_key_here",
        "BIRDEYE_API_KEY": "your_key_here",
        "OPENAI_API_KEY": "your_key_here"
      }
    }
  }
}
```

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
# Blockchain RPC
HELIUS_API_KEY=your_helius_api_key
HELIUS_RPC_URL=https://mainnet.helius-rpc.com/?api-key=your_helius_api_key

# Wallet Management
KEYS_FOLDER=/path/to/your/keys/folder

# Market Data
BIRDEYE_API_KEY=your_birdeye_api_key

# AI Services
OPENAI_API_KEY=your_openai_api_key
XAI_API_KEY=your_xai_api_key

# Optional Configuration
DEFAULT_SLIPPAGE=0.5
MAX_TRANSACTION_RETRIES=3
NETWORK=mainnet-beta
```

### API Key Setup

#### Helius API Key
1. Visit [helius.dev](https://helius.dev)
2. Sign up for a free account
3. Create a new project
4. Copy your API key

#### Birdeye API Key
1. Go to [birdeye.so](https://birdeye.so)
2. Register for developer access
3. Generate an API key from dashboard

#### OpenAI API Key
1. Visit [platform.openai.com](https://platform.openai.com)
2. Create an account
3. Navigate to API keys section
4. Generate a new secret key

### Wallet Configuration

Store your wallet keypairs in the designated folder:

```bash
mkdir -p ~/wonderland-wallets
# Set KEYS_FOLDER=/home/username/wonderland-wallets
```

Each wallet should be a JSON file containing the private key array.

---

## ✨ Features

### 🎨 Token Creation

Create new meme tokens with customizable parameters:

**Parameters:**
- `name`: Token name (e.g., "Wonder Doge")
- `symbol`: Token symbol (3-10 characters)
- `description`: Token description (up to 500 characters)
- `image`: URL or path to token logo
- `twitter` (optional): Twitter handle
- `telegram` (optional): Telegram group link
- `website` (optional): Project website

**Example Usage:**
> "Create a token called 'Moon Cat' with symbol 'MCAT' and description 'The first cat to reach the moon'"

**Response includes:**
- Token mint address
- Transaction signature
- Pump.fun URL
- Initial liquidity information

### 💸 Token Trading

#### Buy Tokens

Purchase tokens directly from the bonding curve:

**Parameters:**
- `tokenAddress`: Mint address of the token
- `amount`: Amount of SOL to spend
- `slippage` (optional): Slippage tolerance (default: 0.5%)

**Example:**
> "Buy 0.5 SOL worth of token at address ABC123..."

#### Sell Tokens

Sell tokens back to the bonding curve:

**Parameters:**
- `tokenAddress`: Mint address of the token
- `amount`: Amount of tokens to sell
- `slippage` (optional): Slippage tolerance

**Example:**
> "Sell all my MCAT tokens"

### 📊 Market Data

#### Trending Tokens

Get real-time trending tokens with comprehensive metrics:

**Response includes:**
- Token name and symbol
- Current price and 24h change
- Trading volume and liquidity
- Market cap and holder count
- Social metrics

**Sorting options:**
- `volume`: Sort by 24h volume
- `marketCap`: Sort by market capitalization
- `priceChange`: Sort by price change
- `holders`: Sort by holder count

#### New Listings

Discover recently launched tokens:

**Filters:**
- `platform`: Filter by launch platform (pump.fun, raydium, etc.)
- `minLiquidity`: Minimum liquidity threshold
- `maxAge`: Maximum age in hours

**Example:**
> "Show me new tokens launched in the last 2 hours with at least $10k liquidity"

### 🎨 AI Image Generation

Generate professional token logos using AI:

**Features:**
- Text-to-image generation
- Multiple style presets
- Transparent background support
- Automatic optimization for tokens

**Style Options:**
- `cartoon`: Fun, meme-friendly style
- `realistic`: Photorealistic rendering
- `pixel`: Retro pixel art
- `abstract`: Modern abstract design

**Example:**
> "Generate a cartoon style logo of a rocket-powered doge flying to the moon"

### 👛 Wallet Management

Comprehensive wallet operations:

- **List Wallets**: View all configured wallets
- **Generate Wallet**: Create new Solana keypairs
- **Check Balance**: Get SOL and token balances
- **Export Wallet**: Safely export wallet credentials
- **Import Wallet**: Import existing wallets

---

## 📚 API Reference

### Core Functions

#### createToken

Creates a new token on Pump.fun.

```typescript
createToken({
  name: string,
  symbol: string,
  description: string,
  image?: string,
  twitter?: string,
  telegram?: string,
  website?: string
}): Promise<{
  signature: string,
  mint: string,
  uri: string
}>
```

#### buyToken

Purchases tokens from the bonding curve.

```typescript
buyToken({
  tokenAddress: string,
  solAmount: number,
  slippage?: number,
  walletAddress?: string
}): Promise<{
  signature: string,
  tokensReceived: number,
  pricePerToken: number
}>
```

#### sellToken

Sells tokens back to the bonding curve.

```typescript
sellToken({
  tokenAddress: string,
  tokenAmount: number,
  slippage?: number,
  walletAddress?: string
}): Promise<{
  signature: string,
  solReceived: number,
  pricePerToken: number
}>
```

#### getTokenInfo

Retrieves detailed token information.

```typescript
getTokenInfo({
  tokenAddress: string
}): Promise<{
  name: string,
  symbol: string,
  supply: number,
  price: number,
  marketCap: number,
  liquidity: number,
  holders: number,
  volume24h: number
}>
```

### Market Data Functions

#### getTrendingTokens

```typescript
getTrendingTokens({
  limit?: number,
  offset?: number,
  sortBy?: 'volume' | 'marketCap' | 'priceChange',
  timeframe?: '1h' | '24h' | '7d'
}): Promise<Token[]>
```

#### getNewListings

```typescript
getNewListings({
  limit?: number,
  platform?: string,
  minLiquidity?: number,
  maxAge?: number
}): Promise<Token[]>
```

#### searchTokens

```typescript
searchTokens({
  query: string,
  limit?: number,
  verified?: boolean
}): Promise<Token[]>
```

### Image Generation Functions

#### generateTokenImage

```typescript
generateTokenImage({
  prompt: string,
  style?: 'cartoon' | 'realistic' | 'pixel' | 'abstract',
  size?: '256x256' | '512x512' | '1024x1024'
}): Promise<{
  url: string,
  localPath: string
}>
```

---

## 🔧 Integration Guides

### Birdeye API Integration

The Birdeye API provides comprehensive market data:

**Available Endpoints:**
- `/defi/price`: Get token prices
- `/defi/trades`: Recent trades
- `/defi/ohlcv`: Price charts
- `/token/trending`: Trending tokens
- `/token/new_listing`: New tokens

**Rate Limits:**
- Free tier: 100 requests/day
- Pro tier: 10,000 requests/day

### OpenAI Integration

Image generation powered by DALL-E 3:

**Best Practices:**
- Use descriptive prompts
- Specify style preferences
- Include "transparent background" for logos
- Request "centered composition"

**Example Prompt:**
```
"A cute cartoon rocket ship with a shiba inu pilot, 
flying through space with stars and planets, 
vibrant colors, transparent background, 
centered composition, suitable for cryptocurrency logo"
```

### Helius RPC Integration

Optimized blockchain interactions:

**Features:**
- Enhanced transaction speed
- Priority fee optimization
- Automatic retry logic
- WebSocket subscriptions

**Configuration:**
```javascript
{
  commitment: 'confirmed',
  preflightCommitment: 'confirmed',
  maxRetries: 3,
  confirmTransactionInitialTimeout: 60000
}
```

---

## 📖 Examples & Tutorials

### Tutorial 1: Launch Your First Meme Token

**Step 1: Generate a Wallet**
> "Generate a new wallet for token creation"

**Step 2: Fund Your Wallet**
> "What's my wallet address? I need to add some SOL"

**Step 3: Create Token Concept**
> "I want to create a space-themed dog token. Can you suggest a name and symbol?"

**Step 4: Generate Logo**
> "Generate a logo for Space Doge - a cartoon shiba inu astronaut floating in space"

**Step 5: Create Token**
> "Create a token called 'Space Doge' with symbol 'SDOGE' using the generated image"

**Step 6: Initial Buy**
> "Buy 1 SOL worth of my new SDOGE token"

### Tutorial 2: Trading Strategies

**Finding Opportunities:**
> "Show me trending tokens sorted by volume with positive 24h change"

**Research Before Buying:**
> "Get detailed info about [token address]"

**Execute Trade:**
> "Buy 0.1 SOL of [token] with 1% slippage"

**Monitor Position:**
> "Check my balance of [token] and current price"

**Take Profits:**
> "Sell 50% of my [token] holdings"

### Advanced Examples

**Bulk Operations:**
```
"Find all tokens with 'moon' in the name, 
then show me the top 5 by market cap"
```

**Complex Searches:**
```
"Search for new tokens launched today 
with over $50k liquidity 
and less than 100 holders"
```

**Portfolio Management:**
```
"List all my token balances 
and calculate total value in SOL"
```

---

## 🔧 Troubleshooting

### Common Issues

#### Transaction Failures

**Problem:** "Transaction simulation failed"

**Solutions:**
- Check wallet balance for sufficient SOL
- Increase slippage tolerance
- Verify token address is correct
- Ensure RPC connection is stable

#### API Connection Issues

**Problem:** "Failed to fetch market data"

**Solutions:**
- Verify API keys are correct
- Check API rate limits
- Test network connectivity
- Ensure environment variables are loaded

#### Image Generation Errors

**Problem:** "Failed to generate image"

**Solutions:**
- Check OpenAI API key and credits
- Simplify prompt if too complex
- Verify file write permissions
- Check disk space availability

### Error Messages

| Error | Cause | Solution |
|-------|-------|----------|
| `InsufficientBalance` | Not enough SOL | Add SOL to wallet |
| `TokenNotFound` | Invalid token address | Verify token exists |
| `SlippageExceeded` | Price moved too much | Increase slippage |
| `NetworkTimeout` | RPC connection issue | Retry or change RPC |
| `InvalidKeypair` | Corrupted wallet file | Regenerate wallet |

### Debug Mode

Enable debug logging:

```env
DEBUG=true
LOG_LEVEL=verbose
```

Check logs at:
```
./logs/wonderland-mcp.log
```

---

## 🔒 Security Best Practices

### Wallet Security

1. **Private Key Storage**
   - Never commit private keys to git
   - Use encrypted storage when possible
   - Limit file permissions: `chmod 600 wallet.json`

2. **Backup Strategy**
   - Keep encrypted backups
   - Use hardware wallets for large amounts
   - Store recovery phrases securely

3. **Transaction Safety**
   - Always verify token addresses
   - Start with small test transactions
   - Double-check slippage settings

### API Key Management

1. **Environment Variables**
   - Never hardcode API keys
   - Use `.env.local` for local development
   - Rotate keys regularly

2. **Access Control**
   - Use separate keys for dev/prod
   - Implement rate limiting
   - Monitor API usage

### Best Practices Checklist

- [ ] Regular security audits
- [ ] Keep dependencies updated
- [ ] Use secure RPC endpoints
- [ ] Implement transaction limits
- [ ] Enable 2FA where available
- [ ] Monitor for suspicious activity

---

## ❓ FAQ

### General Questions

**Q: What is the minimum SOL needed to create a token?**
A: Approximately 0.02 SOL for token creation plus additional SOL for initial liquidity.

**Q: Can I use Wonderland MCP on devnet?**
A: Yes, change the NETWORK environment variable to "devnet".

**Q: How many wallets can I manage?**
A: Unlimited wallets can be stored in your keys folder.

### Trading Questions

**Q: What is slippage?**
A: Slippage is the difference between expected and executed price. Higher slippage allows trades during volatility.

**Q: Can I cancel a pending transaction?**
A: No, Solana transactions are typically confirmed within seconds.

**Q: What happens if a trade fails?**
A: No funds are lost. The transaction is simply rejected.

### Technical Questions

**Q: Can I modify the source code?**
A: Yes, Wonderland MCP is open source. Feel free to fork and customize.

**Q: How do I add custom features?**
A: Extend the TypeScript source files and rebuild the project.

**Q: Is there a rate limit?**
A: Rate limits depend on your API providers (Helius, Birdeye, OpenAI).

### Troubleshooting Questions

**Q: Why is my transaction stuck?**
A: Check network congestion and consider increasing priority fees.

**Q: Images aren't generating?**
A: Verify OpenAI API key and check account credits.

**Q: Market data not loading?**
A: Ensure Birdeye API key is valid and not rate-limited.

---

## 🚀 What's Next?

### Upcoming Features

- 📱 Mobile app integration
- 🤖 Automated trading strategies
- 📊 Advanced charting tools
- 🌐 Multi-chain support
- 🎮 Gamification elements

=
### Contributing

We welcome contributions! Please see our [contributing guidelines](CONTRIBUTING.md).

### Support

Need help? Contact us:
- Email: support@wonderlandmcp.com
- Discord: #support channel
- GitHub Issues: For bug reports

---

**Happy Trading in Wonderland! 🎪✨**
