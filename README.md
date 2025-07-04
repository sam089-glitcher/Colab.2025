##**Exploring Gemini: A Hands-on Guide with Google Generative AI in Colab 🔍🔮**##

This project demonstrates how to integrate and interact with Google's Generative AI (Gemini) models using Python in a Google Colab environment. It includes various functionalities such as text generation, image-to-text generation, embeddings, and chat-based interactions.

🚀 Features
✅ Authenticate and use the Gemini 1.5 Flash model via API

📝 Generate text responses to user prompts

🖼️ Generate descriptions and blogs from an image (Chhatrapati Shivaji Maharaj)

💬 Start and continue chat conversations using a multi-turn chat interface

🔍 Embed text and chat history for semantic search or document retrieval# Colab.2025

📦 Requirements
Install the Google Generative AI client:

pip install -q -U google-generativeai
🔑 Setup

Store your API key securely using Colab's userdata:

from google.colab import userdata
GOOGLE_API_KEY = userdata.get("GEMINI_API_KEY")
genai.configure(api_key=GOOGLE_API_KEY)

🧪 Example Usage

model = genai.GenerativeModel("gemini-1.5-flash")
response = model.generate_content("What is India as a Power")
print(response.text)

🖼️ Image Generation Example
Download and analyze an image:

curl -o image.jpg https://voteforshivajijayanti.com/wp-content/uploads/2024/06/Chhatrapati-Shivaji-Maharaj-1.jpg
Use it with Gemini to generate content:

from PIL import Image
img = Image.open("image.jpg")
response = model.generate_content(img)
print(response.text)

🧠 Embedding Example

result = genai.embed_content(
    model="models/text-embedding-004",
    content="What is India as an emotion",
    task_type="retrieval_document",
    title="Embedding Demo"
)
print(result["embedding"])

💬 Chat Example

chat = model.start_chat(history=[])
response = chat.send_message("How does a computer work?")
print(response.text)
📁 Files Included

welcome_to_colab.py: Python script generated from Colab showing the full implementation

image.jpg: Sample image used for visual prompt input

📌 Notes

This project uses the Gemini 1.5 Flash model

You need a valid Google API Key with the Generative Language API enabled

The code includes both synchronous and streaming responses

🧑‍💻 Author
Saumitra Misra


