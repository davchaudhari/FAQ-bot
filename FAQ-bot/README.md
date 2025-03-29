# InstaQ Bot

![Discord Bot](https://img.shields.io/badge/discord-bot-7289DA.svg)
![Python](https://img.shields.io/badge/python-3.11-blue.svg)
![LlamaIndex](https://img.shields.io/badge/LlamaIndex-0.9.27-green.svg)

A Discord bot that instantly answers questions from your knowledge base using embeddings and semantic search.

## 📖 Overview

InstaQ Bot helps you handle questions efficiently by creating and querying a knowledge base from your documents. The bot uses LlamaIndex for document indexing and semantic search capabilities, making it easy to answer questions accurately based on your uploaded content.

## ✨ Features

- **Document Indexing**: Convert PDF documents and other text files into searchable vector embeddings
- **Semantic Search**: Answer questions based on the content of your indexed documents
- **Discord Integration**: Simple slash commands to query your knowledge base
- **Containerized Deployment**: Easily deploy using Docker

## 🚀 Getting Started

### Prerequisites

- Python 3.11.x
- Discord Bot Token
- OpenAI API Key (for embeddings)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/instaq_bot.git
cd instaq_bot
```

2. Create a virtual environment and install dependencies:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. Create a `.env` file with the following keys:
```
DISCORD_BOT_TOKEN=your_discord_bot_token
OPENAI_API_KEY=your_openai_api_key
```

4. Add your documents to the `data/` directory (PDFs, text files, etc.)

5. Run the bot:
```bash
python bot.py
```

## 💬 Discord Commands

| Command | Description |
|---------|-------------|
| `/query [question]` | Ask a question to search in your knowledge base |
| `/updatedb` | (Commented out in current version) Update the database with new documents |

## 🐳 Docker Deployment

Build and run the bot using Docker:

```bash
docker build -t instaq_bot .
docker run -it --env-file .env instaq_bot
```

## 🛠️ Project Structure

```
instaq_bot/
├── .github/                # GitHub workflow configurations
├── data/                   # Directory for your knowledge base documents
├── storage/                # Storage for vector index
├── bot.py                  # Main Discord bot implementation
├── manage_embedding.py     # Functions for managing document embeddings
├── querying.py             # Query handling functions
├── Dockerfile              # Docker configuration
└── requirements.txt        # Python dependencies
```

## 📋 Technical Details

- Uses LlamaIndex for document parsing and vector embedding
- Embeddings are stored locally in the `storage/` directory
- Built with Discord Interactions API

## 🔧 Advanced Configuration

The bot can be deployed to [fly.io](https://fly.io) using the included `fly.toml` configuration.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Notes

- Make sure to include your documents in the data/ directory
- The OpenAI API may incur costs based on your usage
