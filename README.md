# Tokenized Media Subscription Management System

A comprehensive blockchain-based subscription management system built with Clarity smart contracts for the Stacks blockchain.

## Overview

This system provides a complete solution for managing tokenized media subscriptions, including manager verification, customer onboarding, automated billing, content access control, and retention optimization.

## Smart Contracts

### 1. Subscription Manager Verification (`subscription-manager-verification.clar`)
- Validates and manages subscription managers
- Handles manager verification and revocation
- Tracks verification levels and details

**Key Functions:**
- `verify-manager`: Verify a new subscription manager
- `revoke-manager`: Revoke manager privileges
- `is-verified-manager`: Check if a principal is a verified manager

### 2. Customer Onboarding (`customer-onboarding.clar`)
- Manages customer registration process
- Handles subscription plan selection
- Tracks onboarding completion status

**Key Functions:**
- `register-customer`: Register a new customer with a subscription plan
- `complete-onboarding`: Mark onboarding as complete
- `update-subscription-plan`: Change subscription plan

**Available Plans:**
- Basic: $10/month - HD Streaming, Mobile Access
- Premium: $20/month - 4K Streaming, Multiple Devices, Offline Downloads

### 3. Billing Automation (`billing-automation.clar`)
- Automates subscription billing cycles
- Processes payments and tracks payment history
- Manages billing suspensions

**Key Functions:**
- `setup-billing`: Initialize billing for a customer
- `process-payment`: Process subscription payment
- `suspend-billing`: Suspend billing for a customer

### 4. Content Access (`content-access.clar`)
- Controls access to media content based on subscription
- Tracks content views and user engagement
- Manages content library

**Key Functions:**
- `grant-access`: Grant content access to a user
- `access-content`: Access specific content (with validation)
- `add-content`: Add new content to the library

### 5. Retention Optimization (`retention-optimization.clar`)
- Manages customer loyalty and retention programs
- Awards loyalty points and handles reward redemption
- Tracks engagement metrics and retention risk

**Key Functions:**
- `award-loyalty-points`: Award points to users
- `claim-reward`: Redeem loyalty rewards
- `update-engagement`: Update user engagement metrics
- `create-retention-offer`: Create targeted retention offers

## Features

### 🔐 Manager Verification
- Secure manager verification system
- Role-based access control
- Verification level tracking

### 👥 Customer Management
- Streamlined onboarding process
- Flexible subscription plans
- Easy plan upgrades/downgrades

### 💳 Automated Billing
- Recurring payment processing
- Payment history tracking
- Billing cycle management

### 🎬 Content Access Control
- Subscription-based content access
- View tracking and analytics
- Multi-tier content library

### 🎯 Retention Optimization
- Loyalty points system
- Engagement tracking
- Risk-based retention offers

## Getting Started

### Prerequisites
- Stacks blockchain node
- Clarity CLI tools
- Node.js (for testing)

### Installation

1. Clone the repository
   \`\`\`bash
   git clone <repository-url>
   cd tokenized-media-subscription
   \`\`\`

2. Install dependencies
   \`\`\`bash
   npm install
   \`\`\`

3. Run tests
   \`\`\`bash
   npm test
   \`\`\`

### Deployment

Deploy contracts to Stacks blockchain:

\`\`\`bash
# Deploy manager verification contract
clarinet deploy contracts/subscription-manager-verification.clar

# Deploy customer onboarding contract
clarinet deploy contracts/customer-onboarding.clar

# Deploy billing automation contract
clarinet deploy contracts/billing-automation.clar

# Deploy content access contract
clarinet deploy contracts/content-access.clar

# Deploy retention optimization contract
clarinet deploy contracts/retention-optimization.clar
\`\`\`

## Usage Examples

### Register a New Customer
\`\`\`clarity
(contract-call? .customer-onboarding register-customer u1) ;; Register with Basic plan
\`\`\`

### Process a Payment
\`\`\`clarity
(contract-call? .billing-automation process-payment u1000) ;; Pay $10
\`\`\`

### Access Content
\`\`\`clarity
(contract-call? .content-access access-content u1) ;; Access content ID 1
\`\`\`

### Claim Loyalty Reward
\`\`\`clarity
(contract-call? .retention-optimization claim-reward u1) ;; Claim reward ID 1
\`\`\`

## Error Codes

| Contract | Error Code | Description |
|----------|------------|-------------|
| Manager Verification | u100 | Unauthorized |
| Manager Verification | u101 | Already verified |
| Manager Verification | u102 | Not verified |
| Customer Onboarding | u200 | Unauthorized |
| Customer Onboarding | u201 | Already registered |
| Customer Onboarding | u202 | Invalid plan |
| Billing Automation | u300 | Unauthorized |
| Billing Automation | u301 | Insufficient balance |
| Billing Automation | u302 | Payment failed |
| Content Access | u400 | Access denied |
| Content Access | u401 | Content not found |
| Content Access | u402 | Subscription expired |
| Retention Optimization | u500 | Not eligible |
| Retention Optimization | u501 | Reward already claimed |
| Retention Optimization | u502 | Insufficient loyalty points |

## Testing

The project includes comprehensive tests using Vitest:

\`\`\`bash
npm test                    # Run all tests
npm run test:watch         # Run tests in watch mode
npm run test:coverage      # Run tests with coverage
\`\`\`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, please open an issue in the GitHub repository.
