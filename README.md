# 🤖 RAG Company Policy Chatbot

[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![LangChain](https://img.shields.io/badge/LangChain-Enabled-1C3C3C?style=for-the-badge&logo=chainlink&logoColor=white)](https://python.langchain.com/)
[![Groq](https://img.shields.io/badge/Groq-Powered-f3d03e?style=for-the-badge&logo=lightning&logoColor=black)](https://groq.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

A professional, secure, and highly efficient **Retrieval-Augmented Generation (RAG)** chatbot solution built for corporate environments. This application empowers employees to query internal company policies, SOPs, and handbooks using natural language, providing accurate and context-aware responses backed by verifiable document sources.

---

## 🌟 Key Features

### 🧠 Intelligent RAG Engine
*   **Context-Aware**: Uses **LangChain** and **ChromaDB** to retrieve the most relevant policy snippets before generating answers.
*   **No Hallucinations**: Strictly follows the provided context. If the answer isn't in the policies, it politely declines to guess.
*   **Automatic Sync**: Drop any `.txt` file into the `policy/` directory, and the system automatically vectorizes and embeds it on the next run.

### 🔐 Secure & Modern Auth
*   **Magic Link Login**: Passwordless authentication via email. High security with `itsdangerous` tokenization.
*   **Role-Based Access Control (RBAC)**: Distinct permissions for `admin` and `user` roles.
*   **Session Security**: Automatic chat history cleanup on logout to ensure data privacy.

### ⚡ Premium User Experience
*   **Streaming Responses**: Real-time "typing" effect using Server-Sent Events (SSE) for a ChatGPT-like feel.
*   **Admin Dashboard**: Centralized hub to manage users, update roles, and monitor status.
*   **Responsive UI**: Sleek, modern interface built with vanilla CSS and Jinja2 templates.

---

## 🛠️ Tech Stack

*   **Core Framework**: Flask (Python 3.9+)
*   **LLM Orchestration**: LangChain
*   **Inference Engine**: [Groq](https://groq.com/) (Lightning-fast LPU inference)
*   **Vector Database**: ChromaDB (Persistent storage)
*   **Embeddings**: HuggingFace `all-MiniLM-L6-v2`
*   **Primary Database**: SQLite (User records & transient chat history)
*   **Auth**: Flask-Mail + itsdangerous (Timed tokens)

---

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Muhammad-Naveed342/rag_chatbot_flask_2025.git
cd rag_chatbot_flask_2025
```

### 2. Configure Environment Variables
Create a `.env` file in the root directory and fill in the following:

```env
# Flask Settings
SECRET_KEY=your_super_secret_key

# Groq API (Required for LLM)
GROQ_API_KEY=gsk_your_api_key_here

# Email Configuration (For Magic Links)
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
MAIL_USE_TLS=True
MAIL_USERNAME=your_email@gmail.com
MAIL_PASSWORD=your_app_password
MAIL_DEFAULT_SENDER=your_email@gmail.com
```

### 3. Local Deployment
We recommend using a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

### 4. Docker Deployment
Run the entire stack with a single command:
```bash
docker-compose up --build
```

---

## 📂 Project Structure

```text
├── app.py              # Flask server, Auth routes & API endpoints
├── chatbot.py          # RAG Pipeline (Embeddings, Retrieval, Groq Logic)
├── database.py         # SQLite CRUD operations for users/messages
├── mail_utils.py       # Magic link generation & SMTP logic
├── prompts.yml         # Configurable AI personality & templates
├── policy/             # 📂 SOURCE: Place policy .txt files here
├── policy_db/          # 📂 VECTOR STORE: Persistent ChromaDB files
├── static/             # CSS, JS, and Images
└── templates/          # HTML Templates (Chat, Admin, Login)
```

---

## 📖 Usage Guide

### Admin Panel
1.  Access the `/admin` route (requires admin role).
2.  Add new users by Username and Email.
3.  Activate/Deactivate users or change roles (User/Admin).
4.  Deleted users are immediately logged out and their history wiped.

### Chat Interface
1.  Enter your username and email on the login page.
2.  Click the magic link sent to your email (or use the one printed in the terminal during development).
3.  Ask questions like: *"What is the work-from-home policy?"* or *"How do I apply for leave?"*.

---

## ⚙️ Customization

### Changing AI Personality
You can modify the `prompts.yml` file to change how the chatbot behaves:
- Update `system_prompt` to change tone or company name.
- Modify `policy_prompt_template` to change how the AI presents retrieved information.

### Adding New Policies
Simply upload or copy your `.txt` files into the `/policy` folder. The application uses a `sync_policy_db()` function that detects new files and adds them to the vector store without duplicating existing ones.

---

## 🛡️ Security Note
- **Magic Links**: Tokens expire in 1 hour.
- **Data Persistence**: Chat messages are stored in SQLite but can be wiped upon logout for maximum privacy.
- **Environment**: Never commit your `.env` file. A `.gitignore` is included to protect your credentials.

---

## 🤝 Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License
Distributed under the MIT License. See `LICENSE` for more information.

---
**Developed by [Muhammad Naveed](https://github.com/Muhammad-Naveed342)** 🚀
