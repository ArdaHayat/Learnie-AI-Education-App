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


###  NLP Chatbot (using GPT-like model)
We could be using openai API for the chatbot’s NLP functionality. This simple example shows how to send text to an OpenAI model like GPT and receive responses.

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
