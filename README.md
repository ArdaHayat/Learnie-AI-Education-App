![Learnie Logo](https://github.com/ArdaHayat/Learnie-AI-Education-App/raw/d0619ac613b7e05d587ee7857cdb39bc74822d27/Logo.png)

# Learnie: AI-Powered Education for Kids
Learnie uses AI to create interactive cartoon characters that help children with their homework and studies. 
- Personalized learning through natural language conversations.
- Crypto rewards powered by Solana for gamified learning.
- Visual assistance using computer vision and OCR.

### Features
- AI-powered cartoon characters with unique voices and personalities.
- Solana blockchain integration for rewards and NFT-based customizations.
- Real-time sentiment analysis for engaging interactions.

### Solana Blockchain Integration (Transaction Example)

To interact with the Solana blockchain, you can use the following Python code to transfer tokens:

```python
from solana.account import Account
from solana.rpc.api import Client
from solana.transaction import Transaction
from solana.system_program import TransferParams, transfer

# Connect to the Solana devnet (for testing purposes)
client = Client("https://api.devnet.solana.com")

# Generate a new account (or use an existing one)
sender_account = Account()  # Use sender's private key
receiver_account = Account()  # Use receiver's public key

# Set up transaction to transfer SOL
transaction = Transaction()

# Add a transfer instruction to the transaction
transaction.add(
    transfer(
        TransferParams(
            from_pubkey=sender_account.public_key(),
            to_pubkey=receiver_account.public_key(),
            lamports=1000000000  # Amount in lamports (1 SOL = 1e9 lamports)
        )
    )
)

# Send the transaction
response = client.send_transaction(transaction, sender_account)

# Print the transaction result
print(f"Transaction signature: {response['result']}")

