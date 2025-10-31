# COPYm Architecture Diagram

A comprehensive visual representation of the COPYm platform architecture, illustrating the complete system flow from user registration through tokenization to marketplace operations.

## Overview

This repository contains architectural diagrams documenting the COPYm platform, a blockchain-based asset tokenization and marketplace system. The diagrams visualize the interaction between users, the platform, and on-chain components.

## Architecture Structure

The system is divided into two main sections:

### 🖥️ **COPYM (Platform)**
The off-chain platform that handles user interactions, business logic, and integrations with external services.

### 🔗 **ON-CHAIN**
Blockchain-based components including smart contracts, DID registry, marketplace, and token standards.

## Key Components

### User Roles
- **Issuer**: Asset owners who tokenize and list their assets
- **Investor**: Users who discover and purchase tokens
- **Admin**: System administrators who monitor and manage the platform

### Platform Components
- **Dashboards**: Separate interfaces for Issuers and Investors
- **User Onboarding Flow**: Complete registration and wallet setup process
- **Asset Tokenization Flow**: Process for converting assets into tokens
- **Marketplace Flow**: Trading and purchase operations

### External Services
- **Fireblocks**: Vault creation, wallet management, and secure transactions
- **IPFS (Pinata)**: Decentralized storage for asset metadata
- **Truvera**: Asset verification and custodian services
- **Database**: User and token records storage (MySQL with Prisma ORM)

### On-Chain Components
- **DID Registry**: Decentralized identity management
- **Smart Contracts**: Token minting and management
- **Marketplace**: Token trading platform
- **Token Standards**: ERC-20, ERC-721, ERC-1155, ERC-1400, and custom standards

## User Flows

### 1. User Onboarding
1. **Registration** - User submits registration details
2. **Validation** - Backend validates user information
3. **Database** - Creates user record in database
4. **Vault Creation** - Fireblocks initializes secure vault
5. **Wallet Sync** - Sync wallet addresses
6. **JWT Tokens** - Issue authentication tokens
7. **Dashboard** - Redirect user to appropriate dashboard

### 2. Asset Tokenization
1. **Initiate** - Issuer submits asset metadata
2. **Verification** - Custodian verification (Truvera)
3. **Fireblocks API** - Tokenization engine processes request
4. **Mint Tokens** - Create tokens on blockchain
5. **Link Wallet** - Associate tokens with issuer wallet
6. **Off-Chain Store** - Save token records in database

### 3. Marketplace Flow
1. **Asset Onboarding** - Admin creates asset (`POST /api/assets`)
2. **Token Design** - Define token parameters (`/api/tokens`)
3. **Token Deployment** - Deploy smart contract
4. **Marketplace Listing** - List tokens (`POST /api/marketplace/list`)
5. **Purchase Flow** - Investor purchases (`/api/marketplace/purchase`)
6. **Token Transfer** - Vault to vault transfer
7. **VC Generation** - Create verifiable credential
8. **Post-Purchase** - Update investor portfolio

## API Endpoints

Key API endpoints referenced in the architecture:

- `POST /api/assets` - Create new asset
- `/api/tokens` - Token design and management
- `POST /api/marketplace/list` - List tokens on marketplace
- `/api/marketplace/purchase` - Purchase tokens

## File Structure

```
architectural-diagram/
├── full.html                    # Interactive HTML architecture diagram
├── diagram(1).svg               # Combined SVG architecture diagram
├── registration-flow-diagram.svg # User registration flow (UML sequence diagram)
├── diagram.svg                  # Original registration flow
├── Token-Creation Flow.svg      # Token creation process flow
├── Marketplace-Flow.svg         # Marketplace operations flow
└── README.md                    # This file
```

## Viewing the Diagrams

### HTML Diagram (Recommended)
Open `full.html` in any modern web browser. This provides an interactive, responsive view of the complete architecture with:
- Hover effects on components
- Responsive design for mobile devices
- Visual flow indicators
- Detailed flow steps

### SVG Diagrams
Open any `.svg` file in:
- Web browsers (Chrome, Firefox, Safari, Edge)
- Vector graphics editors (Inkscape, Adobe Illustrator)
- Documentation tools (GitHub, GitLab)

## Technologies & Standards

### Frontend
- Bootstrap 5.3.0
- Font Awesome 6.4.0
- Responsive CSS

### Backend
- Express.js + Node.js
- Prisma ORM
- MySQL Database

### Blockchain
- Fireblocks API
- Smart Contracts
- DID (Decentralized Identifiers)
- Verifiable Credentials (VC)

### Token Standards
- ERC-20 (Fungible tokens)
- ERC-721 (Non-fungible tokens)
- ERC-1155 (Multi-token standard)
- ERC-1400 (Security tokens)
- Custom token standards

### Storage & Services
- IPFS (Pinata) - Decentralized storage
- Truvera - Asset verification
- Fireblocks - Crypto infrastructure

## Features

### Issuer Dashboard
- Token minting initiation
- Asset verification via custodian
- Fireblocks API integration for minting
- Token minting to own wallet
- Marketplace listing capabilities

### Investor Dashboard
- Token discovery and purchase
- Event-driven Fireblocks integration
- Token transfer to investor vault
- Verifiable credential creation

### Common Components
- **Fireblocks Vault**: Secure wallet management
- **DID**: Decentralized identity
- **SBT**: Soulbound tokens/credentials

## Color Scheme

- **Platform Section**: Blue (#4361ee) - Representing off-chain services
- **On-Chain Section**: Pink (#f72585) - Representing blockchain components
- **Emerald Green**: Primary heading color (#059669)

## Notes

- The architecture supports role-based access control (Issuer, Investor, Admin)
- All sensitive operations use Fireblocks for secure key management
- Token metadata is stored on IPFS for decentralization
- The system uses JWT tokens stored in httpOnly cookies for authentication
- Asset verification can be performed via custodian services (marked with ? in tokenization flow)

## License

This architectural documentation is part of the COPYm platform project.

---

**Last Updated**: 2024

For questions or contributions, please refer to the main COPYm project repository.

