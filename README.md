# DecentralTalk - Community-Driven Discussion Protocol

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Clarity](https://img.shields.io/badge/Language-Clarity-blue.svg)](https://clarity-lang.org/)
[![Stacks](https://img.shields.io/badge/Blockchain-Stacks-orange.svg)](https://www.stacks.co/)

> A revolutionary social discourse platform built on Bitcoin's security layer, enabling creators to monetize premium content while fostering authentic community engagement through economic incentives and reputation mechanics.

## 🌟 Vision

DecentralTalk represents the future of decentralized social networks by combining **stake-weighted governance**, **tip-based economics**, and **token-gated premium content** to create sustainable creator economies within Web3 communities.

## 🚀 Core Innovation

Our protocol addresses the fundamental challenges of modern social media:

- **Economic Sustainability**: Direct creator monetization without centralized intermediaries
- **Quality Assurance**: Stake-to-participate model ensures serious discourse
- **Community Governance**: Democratic content curation through voting mechanisms
- **Hierarchical Discussions**: Structured conversation trees for organized discourse
- **Reputation Mining**: Algorithmic scoring based on authentic community engagement

## 🏗️ Architecture Overview

### Key Mechanisms

- **🔒 Stake-to-Participate**: Users must stake STX to create content, ensuring skin in the game
- **💎 Premium Content Gates**: Creators can monetize exclusive discussions and insights
- **💰 Tip Economy**: Direct peer-to-peer value transfer for quality contributions
- **⭐ Reputation Mining**: Dynamic scoring based on community engagement metrics
- **🌳 Nested Threading**: Structured conversations with reply hierarchies
- **🚀 Content Amplification**: Community-driven promotion through boost mechanisms

### Smart Contract Components

```clarity
Core Data Structures:
├── Thread Registry       → Premium content management
├── Reply System         → Hierarchical discussion trees  
├── Reputation Engine    → Community standing metrics
├── Voting System        → Democratic content curation
├── Premium Access       → Monetization gates
├── Staking Mechanism    → Economic participation
└── Content Amplification → Community-driven promotion
```

## 📋 Features

### ✅ Implemented Features

- [x] **Thread Creation** - Stake-gated discussion initialization
- [x] **Reply System** - Nested conversation hierarchies
- [x] **Premium Access** - Token-gated exclusive content
- [x] **Reputation Engine** - Dynamic community scoring
- [x] **Voting Mechanisms** - Democratic content curation
- [x] **Staking System** - Economic participation requirements
- [x] **Platform Fees** - Sustainable revenue model

### 🔄 In Development

- [ ] **Voting Implementation** - Complete upvote/downvote functionality
- [ ] **Tip Economy** - Direct creator compensation system
- [ ] **Content Moderation** - Community-driven thread locking
- [ ] **NFT Milestones** - Achievement-based token rewards
- [ ] **Boost System** - Content amplification mechanics
- [ ] **Advanced Analytics** - Comprehensive reputation tracking

## 🛠️ Technical Specifications

### Smart Contract Details

| Component | Purpose | Key Features |
|-----------|---------|--------------|
| **Thread Management** | Content organization | Premium gates, voting, tips |
| **Reply System** | Nested discussions | Parent-child relationships |
| **Reputation Engine** | Community scoring | Algorithmic calculation |
| **Access Control** | Premium monetization | STX-based payments |
| **Staking Mechanism** | Participation gates | Minimum stake requirements |

### Economic Model

```clarity
Platform Economics:
├── Minimum Stake: 1 STX (1,000,000 µSTX)
├── Platform Fee: 2.5% on premium purchases
├── Creator Revenue: 97.5% of premium sales
└── Tip Distribution: 100% to content creators
```

### Error Handling

The contract implements comprehensive error handling with descriptive constants:

- `ERR_INSUFFICIENT_STAKE` - User must stake minimum STX amount
- `ERR_THREAD_NOT_PREMIUM` - Access denied to premium content
- `ERR_INVALID_PARENT_REPLY` - Reply hierarchy validation failed
- `ERR_THREAD_LOCKED` - Content moderation restrictions
- `ERR_UNAUTHORIZED` - Permission validation failed

## 🚀 Getting Started

### Prerequisites

- [Clarinet](https://github.com/hirosystems/clarinet) for local development
- [Node.js](https://nodejs.org/) for testing framework
- [Stacks CLI](https://docs.stacks.co/docs/cli) for deployment

### Installation

```bash
# Clone the repository
git clone https://github.com/elijah-cmake/decentral-talk.git
cd decentral-talk

# Install dependencies
npm install

# Run contract checks
clarinet check
```

### Local Development

```bash
# Start local testnet
clarinet integrate

# Run tests
npm test

# Deploy to testnet
clarinet deploy --testnet
```

## 📊 Usage Examples

### Creating a Thread

```clarity
;; Create a public discussion thread
(contract-call? .decentral-talk create-thread 
  "Web3 Social Media Evolution" 
  "Discussing the future of decentralized social platforms..."
  false  ;; not premium
  u0     ;; no premium price
)

;; Create a premium content thread
(contract-call? .decentral-talk create-thread 
  "Exclusive: DeFi Alpha Strategies" 
  "Premium insights into yield farming opportunities..."
  true   ;; premium content
  u5000000  ;; 5 STX access price
)
```

### Participating in Discussions

```clarity
;; Reply to a thread
(contract-call? .decentral-talk create-reply 
  u1  ;; thread-id
  "Great insights! I'd like to add..."
  none  ;; no parent reply (top-level)
)

;; Reply to another reply (nested)
(contract-call? .decentral-talk create-reply 
  u1     ;; thread-id
  "I disagree with this point because..."
  (some u1)  ;; replying to reply-id 1
)
```

### Accessing Premium Content

```clarity
;; Purchase access to premium thread
(contract-call? .decentral-talk purchase-premium-access u2)
```

## 🧪 Testing

The project includes comprehensive test suites covering:

- Thread creation and validation
- Reply system and hierarchies
- Premium access controls
- Reputation calculations
- Staking mechanisms
- Error handling scenarios

```bash
# Run all tests
npm test

# Run specific test file
npm test -- --testNamePattern="thread creation"

# Check contract syntax
clarinet check
```

## 🔐 Security Considerations

### Access Controls

- **Stake Validation**: All content creation requires minimum STX stake
- **Premium Gates**: Payment verification for exclusive content access
- **Parent Reply Validation**: Ensures reply hierarchy integrity
- **Double-Purchase Prevention**: Blocks duplicate premium access purchases

### Economic Security

- **Platform Fee Structure**: Sustainable 2.5% fee on premium transactions
- **Stake Requirements**: Minimum 1 STX stake prevents spam
- **Treasury Management**: Secure platform fee collection

## 🌐 Deployment

### Testnet Deployment

```bash
# Deploy to Stacks testnet
clarinet deploy --testnet

# Verify deployment
clarinet console --testnet
```

### Mainnet Deployment

```bash
# Deploy to Stacks mainnet
clarinet deploy --mainnet

# Monitor deployment
stx balance <contract-address>
```

## 📈 Roadmap

### Phase 1: Core Infrastructure ✅

- [x] Thread and reply system
- [x] Premium access controls
- [x] Basic reputation tracking
- [x] Staking mechanisms

### Phase 2: Community Features 🔄

- [ ] Complete voting implementation
- [ ] Tip economy deployment
- [ ] Content moderation tools
- [ ] Advanced reputation metrics

### Phase 3: Advanced Economics 📋

- [ ] NFT milestone system
- [ ] Content boost mechanisms
- [ ] Governance token integration
- [ ] Cross-chain compatibility

### Phase 4: Ecosystem Expansion 🌟

- [ ] Mobile application
- [ ] Web3 integrations
- [ ] Creator analytics dashboard
- [ ] Enterprise partnerships

## 🤝 Contributing

We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Standards

- Follow Clarity best practices
- Include comprehensive tests
- Document all public functions
- Use descriptive variable names
- Implement proper error handling

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Stacks Foundation](https://stacks.org/) for blockchain infrastructure
- [Clarity Language](https://clarity-lang.org/) for smart contract capabilities
- [Bitcoin](https://bitcoin.org/) for the security layer
- Our amazing community of contributors and early adopters

---

## Built with ❤️ by the DecentralTalk team

*Empowering creators, connecting communities, securing conversations on Bitcoin.*
