# Denver KYC Token

##Transaction ID: at1ngwn48vy4d52grq29eljj2nelhy4mz3nj374wwpkh0f6cx8ayvpsrgguaq

## Overview
The `denver_kyc_token.aleo` contract implements a compliant token system with built-in spending limits and external authorization requirements. This ensures that token transactions adhere to predefined compliance rules, making it suitable for regulatory-compliant financial applications.

## Compliance Feature
The contract enforces compliance through:
- **Spending Limits:** Users have a daily transaction cap to prevent excessive transfers.
- **External Authorization:** Transactions require validation by an external authority, ensuring oversight.
- **Token Registration:** The token is registered with a trusted registry before issuance.
- **Controlled Minting:** Only the admin can mint tokens, preventing unauthorized inflation.

## How It Works
1. **Token Initialization:** The admin registers the token in the `token_registry.aleo` to enforce external authorization.
2. **Minting:** The admin mints a fixed supply of tokens for controlled distribution.
3. **Issuing Spend Limits:** The admin assigns daily spending limits to users.
4. **Private Transfers:** Users can transfer tokens while ensuring they stay within their daily spending limits.
5. **Finalization:** Transactions await confirmation before completion, ensuring integrity.

## Deployment Instructions
1. **Compile the Contract:**
   ```sh
   leo build
   ```
2. **Deploy the Contract:**
   ```sh
   leo deploy
   ```
3. **Initialize the Token (Admin Only):**
   ```sh
   leo run initialize
   ```
4. **Mint Tokens (Admin Only):**
   ```sh
   leo run mint_private
   ```
5. **Issue a Spend Limit:**
   ```sh
   leo run issue_limit <user_address>
   ```
6. **Transfer Tokens Privately:**
   ```sh
   leo run transfer_private <input_token> <spend_limit> <amount> <recipient> <epoch>
   ```

## Intended Use Case
This contract is designed for applications requiring **regulatory-compliant digital assets** with controlled transactions, such as:
- **KYC-Compliant Payment Systems**
- **Corporate Expense Management**
- **Government-Approved Digital Currencies**

By enforcing spending limits and external authorization, it ensures a **secure, compliant, and controlled** financial ecosystem.

