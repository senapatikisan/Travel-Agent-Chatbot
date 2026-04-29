🧳 **Travel Assistant Chatbot** (LangChain + Gemini)
A conversational AI-powered travel assistant built using LangChain and Google Gemini (Generative AI).
The bot answers only travel-related questions and maintains a compressed conversational memory to track user preferences efficiently.

📌 **Features**

✈️ Answers travel-related queries only (flights, hotels, destinations, itineraries, budgets, packing tips).
🚫 Responds with “I can't help with it.” for non-travel questions.
🧠 Conversation memory summarization every 5 turns to prevent context overflow.
💬 Streams responses token-by-token for a smooth chat experience.
🔐 Loads API credentials securely using .env.


🧠 **Architecture Overview**
1. Primary Travel Assistant

Uses Google Gemini (gemini-2.5-flash) via LangChain.
Enforced by a system prompt to restrict answers strictly to travel topics.

2. Conversation Memory Summarizer

A second Gemini model compresses older messages into a short summary.
Keeps:

User travel preferences
Confirmed trip details
Constraints
Open questions


Prevents hallucination by explicitly not inventing facts.


📂 Project Structure
.
├── travel-bot.py        # Main chatbot implementation
├── .env                 # Environment file for API keys (not committed)
└── README.md            # Project documentation


⚙️ Requirements
Python

Python 3.9+ recommended

Dependencies
Install the required libraries using:
Markdownpip install python-dotenv langchain langchain-google-genaiShow more lines

🔐 Environment Setup
Create a .env file in the project root:
Plain Textenv isn’t fully supported. Syntax highlighting is based on Plain Text.GOOGLE_API_KEY=your_google_api_key_hereShow more lines

⚠️ Do not commit .env to GitHub.


▶️ How to Run


Clone the repository:
Shellgit clone https://github.com/<your-username>/<repo-name>.gitcd <repo-name>Show more lines


Install dependencies:
Shellpip install -r requirements.txtShow more lines
(or install manually if you don’t have a requirements.txt yet)


Start a Python session:
ShellpythonShow more lines


Chat with the bot:
Pythonfrom travel_bot import chatchat("I want a budget-friendly 3-day trip from Dallas to Destin")Show more lines



🧪 Example Behavior





















User InputBot Response“Suggest cheap food options in Destin”✅ Travel advice“What is Machine Learning?”❌ I can’t help with it.“What all can you help with?”✅ Lists travel-related topics

🧠 Memory Management Logic

Conversation is summarized every 5 user turns
Only the last 2 messages + compressed memory are retained
Summary is injected as a SystemMessage for continuity

This keeps the chatbot:

✅ Context-aware
✅ Token-efficient
✅ Scalable for long conversations


🚀 Possible Enhancements

Add a CLI loop for continuous chat
Integrate a frontend (Streamlit / FastAPI)
Store conversation summaries in a database
Add location-aware recommendations
Add multi-user session handling


🧑‍💻 Author
Kisan Senapati
GitHub: https://github.com/senapatikisan
