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


### NLP Chatbot (using GPT-like model)
We could be using openai API for the chatbot’s NLP functionality. This simple example shows how to send text to an OpenAI model like GPT and receive responses.

    import openai


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

### This code demonstrates the base. The communication/animation function using microphones would need capital.
 - This is a simple integration with OpenAI’s GPT model.
 - You input a query, and the bot returns a response.
 - You can tweak this for your app to make it more specific to educational tasks.



### OCR Functionality (using Tesseract OCR)
For Optical Character Recognition (OCR), could use Tesseract OCR with the pytesseract Python library to extract text from images.

        import pytesseract
        from PIL import Image

        # Path to the Tesseract executable (change this based on your installation path)
        pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"

        def ocr_from_image(image_path):
        # Open an image file
        img = Image.open(image_path)
        
        # Use Tesseract to do OCR on the image
        text = pytesseract.image_to_string(img)
    
        return text

        # Example usage
        image_path = 'example_image.png'  # Replace with your image path
        extracted_text = ocr_from_image(image_path)
        print(f"Extracted Text: {extracted_text}")

### Explanation:

 - This code extracts text from an image.
 - You would use this feature to scan homework or educational materials and extract text.
 - Replace the image_path with the actual path to the image you want to process.


### Blockchain Integration (using Solana with our understanding)
 - For integrating Solana blockchain into Solana app, you'll need to use Solana’s SDK for Python or JavaScript.


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
 - This is a simple example of transferring SOL between accounts on Solana’s devnet.
 - You can adjust this to use Solana tokens or create a reward system where users earn tokens (paid through 
   the blockchain).
 - Replace sender_account and receiver_account with actual wallets in your app.

