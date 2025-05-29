# Wonderland-MCP-Automated-TokenLauncher
The official Github of the Wonderland MCP Pump Fun Automated Token Launcher with Bundle Protection

A powerful Model Context Protocol (MCP) server for interacting with [Pump.fun](https://pump.fun) tokens on the Solana blockchain. This project allows you to create, buy, sell, and manage tokens through Claude Desktop using the MCP protocol.

## Features

### Core Token Management

- **Create Token**: Create new tokens on Pump.fun with customizable name, symbol, description, and image
- **Buy Token**: Purchase existing Pump.fun tokens with SOL
- **Sell Token**: Sell tokens back to the bonding curve for SOL
- **Get Token Info**: Retrieve detailed information about existing tokens
- **Get Account Balance**: Check SOL and token balances for accounts

### Market Data (Birdeye API Integration)

- **Get Trending Tokens**: View a list of trending tokens with detailed market metrics
- **Get New Listings**: Discover newly listed tokens on various platforms including Pump.fun
- **Search Tokens**: Search for tokens by name, symbol, or address with advanced filtering options

### Token Image Generation (OpenAI Integration)

- **Generate Token Image**: Create professional token logos using OpenAI's image generation model
- **Edit Token Image**: Modify existing token images with AI-assisted editing
- **Upload Token Image**: Save and retrieve token images for use with Pump.fun

### Wallet Management

- **List Accounts**: View all accounts in your keys folder
- **Generate Wallet**: Create new Solana wallets
- **Check SOL Balance**: Verify the SOL balance of any wallet

## Setup

### Prerequisites
- Node.js or Bun installed
- Claude Desktop with MCP support

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
HELIUS_API_KEY=your_helius_api_key
KEYS_FOLDER=/path/to/keys/folder
BIRDEYE_API_KEY=your_birdeye_api_key
XAI_API_KEY=your_xai_api_key
HELIUS_RPC_URL=https://mainnet.helius-rpc.com/?api-key=your_helius_api_key
OPENAI_API_KEY=your_openai_api_key
```

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/pump-mcp.git
cd pump-mcp

# Install dependencies
bun install

# Build the project
bun run build
```

## Usage

1. Start Claude Desktop
2. Connect to this MCP server
3. Use natural language to interact with the available tools

## API Integrations

### Birdeye API

- Trending tokens with market data and price information
- New token listings across various platforms
- Token search functionality with filtering options

### OpenAI API

- Generating professional token logos based on token description
- Editing existing token images with transparent backgrounds
- Images are saved to `/Users/8bit/Downloads/PUMP-MCP-main/generated-images`

### Helius API

The Helius API provides RPC access to the Solana blockchain for all token operations.

## Example Prompts

- "Create a new token called 'Rocket Coin' with symbol 'RKT'"
- "Show me trending tokens sorted by volume"
- "Get the latest token listings on Pump.fun"
- "Search for tokens containing 'sol' in their name"
- "Generate a token image for a space-themed cryptocurrency"
- "Buy 0.1 SOL worth of token at address XYZ"
- "Sell all my tokens for address ABC"

## Development

```bash
# Make your changes to the TypeScript files in src/

# Build the project
bun run build

# Run the server
node build/index.js
```

## License

ISC
