# 🤖 RAG Company Policy Chatbot
Here it is Chat bot project used LangChain Framework and integration with  Groq API  used Flask API login with Magic Mail Link A RAG (Retrieval-Augmented Generation) chatbot is an AI assistant that links a Large Language Model (LLM) to your own private or specific data to provide more accurate and up-to-date answers. 
.........................
🌟 Key Features

🧠 Advanced RAG Architecture: Utilizes LangChain and Hugging Face  for efficient retrieval of policy information.

⚡ High-Performance LLM: Powered by Groq for lightning-fast response generation.

🔐 Magic Link Authentication: Secure, passwordless login system using email verification.

🛡️ Admin Dashboard: Full User Management system for admins to add, update, or delete users and manage roles.

💬 Streaming Interface: Modern, responsive chat UI with real-time "typing" effect (Server-Sent Events).

📂 Automatic Document Sync: Automatically detects new .txt files in the policy/ directory and updates the vector database.
...................................
🐳 Dockerized: Easy deployment using Docker and Docker Compose.
......................................
🛠️ Tech Stack
.......................................
Backend: Flask (Python)
AI Framework: LangChain
Vector Database: ChromaDB
LLM Provider: Groq (Llama 3 / Mixtral)
Embeddings: HuggingFace (all-MiniLM-L6-v2)
Database: SQLite (User management & Chat history)
Styling: Vanilla CSS with modern UI components
🚀 Getting Started
1. Prerequisites
Python 3.9+
Docker (optional)
A Groq API Key (Get one here)
2. Installation
Clone the repository and install dependencies:

git clone https://github.com/Muhammad-Naveed342/rag_chatbot_flask_2025.git
cd rag_chatbot_flask_2025
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
3. Policy Data
Place your company policy files (.txt) inside the policy/ directory. The system will automatically embed them on the first run.

5. Running the Application
python app.py
Access the app at http://localhost:5000.

🐳 Docker Deployment
To run the entire stack using Docker:

docker-compose up --build
📂 Project Structure
app.py: Main Flask application and API routes.
chatbot.py: Core RAG logic, embeddings, and LLM integration.
database.py: SQLite database management for users and chat history.
mail_utils.py: Magic link generation and email logic.
prompts.yml: Configurable system prompts and templates.
policy/: Directory for source policy documents.
policy_db/: Persistent storage for ChromaDB.
static/ & templates/: Frontend assets and HTML.
🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

📄 License
Distributed under the MIT License. See LICENSE for more information.
