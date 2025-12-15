# Simple-Chatbot-using-Google-Gemini-API
This project is a lightweight and extendable chatbot built with the Google Gemini API. It takes user input, sends it to the Gemini 2.5 Flash model, and returns an intelligent response.

# Features

Conversation history support

Uses Gemini 2.5 Flash model

Stable performance in Google Colab

Clean and extendable codebase

# Installation
1-1 Install the official Gemini SDK:
pip install google-genai

1-2 Add Your API Key:
Get your API Key from ai.google.dev and place it in the script.

1-3 📁 Project Structure
project/
│── chatbot.py
│── README.md

# 🧠 Usage Example

from google import genai
client = genai.Client(api_key="YOUR_API_KEY")
messages = []
while True:
    user_input = input("User: ")
    if user_input.lower() in ["exit", "quit"]:
        break

    messages.append({"role": "user", "content": user_input})

    response = client.models.generate_content(
        model="gemini-2.5-flash",
        messages=messages,
    )

    reply = response.text
    print("Bot:", reply)

    messages.append({"role": "assistant", "content": reply})

