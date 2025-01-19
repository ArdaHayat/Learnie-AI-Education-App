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


### Explanation:
- Use triple backticks (```) to create a code block, followed by the programming language name (in this case, `python`) for syntax highlighting.
- The code itself is placed between the backticks.

### 2. **Steps to Edit `README.md`**:

1. Open your GitHub repository.
2. Navigate to the `README.md` file.
3. Click on the **pencil icon** to edit the file.
4. Paste the code sample into the file.
5. Commit the changes.

After committing, the code will appear as a properly formatted block in your `README.md` when viewed on GitHub.

### 3. **View Example in `README.md`**:
Once you push the changes to your GitHub repo, your `README.md` will display the code snippet like this:

---

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


### NLP Chatbot (Using GPT-like model)

We could be using openai API for the chatbot’s NLP functionality. This simple example shows how to send text to an OpenAI model like GPT and receive responses.:

import openai

# Your OpenAI API key (make sure to replace it with your actual key)
openai.api_key = 'your-api-key'

def chat_with_learnie(user_input):
    response = openai.Completion.create(
        engine="text-davinci-003",  # Can be adjusted based on the model
        prompt=user_input,
        max_tokens=100,  # Limits the response size
        n=1,
        stop=None,
        temperature=0.7,  # Controls the randomness of the response
    )

    # Returning the chatbot's response
    return response.choices[0].text.strip()

# Example usage
user_input = "What is the capital of France?"
response = chat_with_learnie(user_input)
print(f"Learnie: {response}")
