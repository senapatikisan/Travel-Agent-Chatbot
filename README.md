# 🧳 Travel Assistant Chatbot (LangChain + Gemini)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-enabled-green)
![Gemini](https://img.shields.io/badge/Google%20Gemini-gemini--2.5--flash-orange)
![License](https://img.shields.io/badge/License-MIT-blue)
![Status](https://img.shields.io/badge/Status-Active-success)

A conversational **AI-powered travel assistant** built using **LangChain** and **Google Gemini (Generative AI)**.

The bot answers **only travel-related questions** and maintains **compressed conversational memory** to track preferences efficiently over long interactions.

---

## 📌 Features

- ✈️ Responds only to **travel-related queries**, including:
  - Flights
  - Hotels & accommodations
  - Destinations
  - Itineraries
  - Budgets
  - Packing advice
- 🚫 For non-travel questions, responds with:
  
  I can't help with it.

- 🧠 Automatically **summarizes conversation memory every 5 turns**
- 💬 Streams responses in real time
- 🔐 Secure API key handling using `.env`

---

## 🧠 Architecture Overview

### Travel Assistant
- Powered by **Google Gemini (gemini-2.5-flash)**
- Strict system prompt limits responses to travel topics only

### Memory Summarizer
- Uses a second Gemini model
- Stores:
  - User travel preferences
  - Confirmed trip details
  - Constraints
  - Open questions
- Prevents hallucinations by explicitly avoiding invented facts
- Keeps only:
  - A compressed summary
  - The last 2 conversation turns

---

## 📂 Project Structure

    .
    ├── travel-bot.py        # Main chatbot implementation
    ├── .env                # Environment variables (not committed)
    └── README.md           # Documentation

---

## ⚙️ Requirements

### Python
- Python **3.9 or higher**

### Dependencies

Install required packages:

    pip install python-dotenv langchain langchain-google-genai

---

## 🔐 Environment Setup

Create a file named `.env` in the project root and add:

    GOOGLE_API_KEY=your_google_api_key_here

⚠️ Do NOT commit your `.env` file to GitHub.

---

## ▶️ Usage

Start a Python session or script and call the `chat()` function:

    from travel_bot import chat
    chat("I want a budget-friendly 3-day trip from Dallas to Destin")

Responses will stream live to the console.

---

## ✅ Example Behavior

User Input:  
Suggest cheap food options  

Bot Response:  
✅ Travel-related advice

User Input:  
What is Machine Learning?  

Bot Response:  
❌ I can't help with it.

---

## 🧠 Memory Strategy

- Conversation memory is summarized every **5 user turns**
- Prevents token overuse
- Enables long, context-aware conversations
- Suitable for production-style chat usage

---

## 🚀 Possible Enhancements

- Interactive CLI loop
- Web UI using Streamlit or FastAPI
- Persistent memory storage (Redis / database)
- Multi-user session support
- Location-aware recommendations

---

## 🧑‍💻 Author

Kisan Senapati  
GitHub: https://github.com/senapatikisan
