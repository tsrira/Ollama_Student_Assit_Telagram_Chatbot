# 🧠 Jain University Student Assistant Bot (n8n + Telegram + Ollama)

This project integrates [n8n](https://n8n.io), [Telegram Bot API](https://core.telegram.org/bots), and Ollama's Llama3.2:3B Model to provide a **smart, automated FAQ assistant** for Jain University students. The assistant answers queries using a vectorized version of the official student handbook.

---

## 🚀 Features

- ✅ Real-time question answering via Telegram
- 📄 Uses a curated [Student Handbook PDF](./Jain_University_Student_Handbook_FAQs.pdf) as the source of truth
- 🔍 Embedding and semantic search using Pinecone + OpenAI
- ⚙️ Built on n8n (no-code/low-code automation)
- 💬 Chat memory support for context
- 🧾 Response constrained to uploaded content (no hallucinations)

---

## 📲 Live Demo

🎯 Try it here → [SriramAIStudentAssist_Bot](https://t.me/SriramAIStudentAssist_Bot)

> Ask questions like:  
> - *What is the attendance requirement?*  
> - *Are hostel facilities available?*  
> - *Is there a refund policy for withdrawals?*

and the quick demo of the telegram here -> [Jain University Student Assist Bot - Demo](https://youtu.be/52Nk_fOpX38)

---

## 📂 Project Structure

| File | Description |
|------|-------------|
| `Student Assistant.json` | n8n workflow for handling Telegram messages and AI responses |
| `Vector Creation Student.json` | n8n workflow for extracting content from PDF and storing embeddings in Pinecone |
| `Jain_University_Student_Handbook_FAQs.pdf` | Official FAQ content used as vector store |
| `README.md` | Project description and setup guide |

---

## 🧱 Tech Stack

- **n8n**: Automation orchestrator
- **Telegram Bot**: User interface for queries
- **OpenAI (GPT-4.1)**: Language model for understanding and summarizing responses
- **Pinecone**: Vector store for similarity search
- **Google Drive**: File trigger for document ingestion

---

## 📦 How It Works

1. **Document Vectorization**  
   - Triggers when a file is uploaded to Google Drive  
   - Splits PDF into chunks → Converts to vectors using OpenAI Embeddings  
   - Stores vectors in Pinecone (Vector DB)

2. **Telegram Bot Assistant**  
   - Listens to Telegram messages via webhook  
   - Runs query against Pinecone vector store  
   - Uses AI Agent node to summarize relevant content  
   - Sends accurate answer (or fallback message) to student

---

## 🤖 System Message Constraints

> The assistant strictly answers *only* from the content of the handbook. If no relevant information is found, it replies:
> ```
> Sorry! I can't find relevant information from the knowledge base.
> ```

---

## 📌 Sample Query

**User:**  
> What is the attendance policy for Engineering students?

**Bot:**  
> Engineering students are required to maintain a minimum of 85% attendance. Up to 10% may be condoned by the dean to bring it down to 75%. Falling below the minimum leads to removal from the rolls.

---

## 🧑‍🎓 Ideal Use Cases

- Student Helpdesks  
- University FAQ bots  
- Academic document search  
- FAQ support without hallucinations

---

## 🔐 Credentials Needed

- OpenAI API Key  
- Telegram Bot Token  
- Pinecone API Key  
- Google Drive OAuth Credentials

---

## 🛠️ Setup Instructions

1. Clone the repository
2. Import `.json` workflows into your n8n instance
3. Configure credentials for:
   - Telegram
   - OpenAI
   - Pinecone
   - Google Drive
4. Deploy the bot and test by sending messages to your Telegram bot

---

## 📄 License

MIT License

---

## ✨ Credits

Developed as part of a student automation assignment using real-time university handbook data for **Jain University, Bangalore**.
