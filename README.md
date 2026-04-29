# 🧳 Travel Assistant Chatbot (LangChain + Gemini)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-%E2%9C%93-green)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-gemini--2.5--flash-orange)
![License](https://img.shields.io/badge/License-MIT-blue)
![Status](https://img.shields.io/badge/Status-Active-success)

A conversational **AI-powered travel assistant** built using **LangChain** and **Google Gemini (Generative AI)**.  
The bot answers **only travel-related questions** and maintains a **compressed conversational memory** to track user preferences efficiently.

---

## 📌 Features

- ✈️ Answers **travel-related queries only**
  - Flights
  - Hotels & stays
  - Destinations
  - Itineraries
  - Budgets
  - Packing tips
- 🚫 Responds with **"I can't help with it."** for non-travel questions
- 🧠 **Conversation memory summarization** every 5 turns
- 💬 **Streaming responses** for real-time interaction
- 🔐 Secure API key management using `.env`

---

## 🧠 Architecture Overview

### 🔹 Travel Assistant
- Powered by **Google Gemini (`gemini-2.5-flash`)**
- Strict system prompt ensures responses stay within travel scope

### 🔹 Memory Summarizer
- Second Gemini model compresses older messages
- Maintains:
  - User preferences (budget, dates, travel mode)
  - Confirmed trip details
  - Constraints
  - Open questions
- Prevents hallucination by explicitly **not inventing facts**

---

## 📂 Project Structure
