# 📚 Knowledge Hub

A prototype web application that allows users to ask questions and receive informed answers from a curated knowledge base.

## Features

- 🔍 **Smart Question Processing**: Ask questions in natural language and get relevant answers
- 📖 **Knowledge Base**: Pre-loaded with articles on programming, web development, databases, APIs, cloud computing, and more
- 🎯 **Intelligent Search**: Finds the most relevant articles based on your question
- 💡 **Suggested Questions**: Quick-start with pre-made questions
- 📑 **Source Citations**: See which articles were used to generate your answer
- 🏷️ **Topic Browsing**: Explore available topics and categories
- 🎨 **Modern UI**: Beautiful, responsive interface that works on all devices

## Tech Stack

- **Backend**: Python Flask
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Knowledge Base**: Embedded articles with search and matching algorithms
- **Styling**: Modern CSS with gradients and animations

## Quick Start

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Installation

1. **Navigate to the project directory**
   ```bash
   cd Searches
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment**
   
   On Windows:
   ```bash
   venv\Scripts\activate
   ```
   
   On macOS/Linux:
   ```bash
   source venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

### Running the Application

**Option 1: Using the run script**

On Windows:
```bash
run_knowledge_hub.bat
```

On macOS/Linux:
```bash
chmod +x run_knowledge_hub.sh
./run_knowledge_hub.sh
```

**Option 2: Direct Python command**
```bash
python knowledge_hub.py
```

5. **Open your browser**
   
   Navigate to: `http://localhost:5000`

6. **Start asking questions!**
   
   - Type your question in the input field
   - Click "Ask Question" or press Enter
   - View the answer with sources and related topics
   - Try the suggested questions for quick examples

## Usage Examples

### Example Questions

- "What is Python programming?"
- "How do I design a database?"
- "What are RESTful APIs?"
- "Explain machine learning basics"
- "What is Docker?"
- "How does version control work?"
- "What are web security best practices?"
- "What is cloud computing?"

### Features in Detail

**Question Processing**
- Natural language understanding
- Keyword matching and relevance scoring
- Multi-article answer synthesis

**Answer Generation**
- Combines information from multiple relevant articles
- Provides confidence levels (high, medium, low)
- Includes source citations

**Topic Browsing**
- Browse available categories
- Click topics to ask related questions
- View all available tags

## API Endpoints

### `GET /`
Serves the main Knowledge Hub interface.

### `POST /api/ask`
Ask a question and receive an answer.

**Request Body:**
```json
{
  "question": "What is Python programming?"
}
```

**Response:**
```json
{
  "success": true,
  "query": "What is Python programming?",
  "answer": "Based on the knowledge base, here's what I found...",
  "confidence": "high",
  "sources": [
    {
      "title": "Python Programming Basics",
      "category": "Programming",
      "id": "python-basics"
    }
  ],
  "related_topics": ["Programming", "Web Development"],
  "timestamp": "2024-01-15T10:30:00"
}
```

### `GET /api/search?q=<query>`
Search for articles in the knowledge base.

### `GET /api/topics`
Get all available topics and categories.

### `GET /api/article/<article_id>`
Get a specific article by ID.

### `GET /api/health`
Health check endpoint.

## Knowledge Base

The knowledge base includes articles on:

- **Programming**: Python, general programming concepts
- **Web Development**: Frontend, backend, full-stack
- **Data Science**: Machine learning, AI basics
- **Database**: Design principles, SQL, NoSQL
- **API Development**: RESTful APIs, best practices
- **Development Tools**: Git, version control
- **Cloud Computing**: AWS, Azure, GCP
- **Security**: Web security fundamentals
- **DevOps**: Docker, containerization
- **Quality Assurance**: Testing strategies

## Customization

### Adding New Articles

Edit `knowledge_hub.py` and add entries to the `KNOWLEDGE_BASE` list:

```python
{
    "id": "unique-id",
    "title": "Article Title",
    "category": "Category Name",
    "content": "Article content here...",
    "tags": ["tag1", "tag2", "tag3"]
}
```

### Modifying Search Algorithm

The search algorithm in the `KnowledgeHub` class can be customized:
- Adjust scoring weights
- Add new matching criteria
- Implement advanced NLP features

### Styling

Modify `static/knowledge_hub.css` to customize the appearance.

## Project Structure

```
.
├── knowledge_hub.py          # Flask backend application
├── static/
│   ├── knowledge_hub.html    # Main HTML page
│   ├── knowledge_hub.css     # Styling
│   └── knowledge_hub.js      # Frontend JavaScript
├── requirements.txt          # Python dependencies
├── run_knowledge_hub.bat     # Windows run script
├── run_knowledge_hub.sh      # Linux/Mac run script
└── KNOWLEDGE_HUB_README.md   # This file
```

## Troubleshooting

### Port Already in Use
If port 5000 is already in use:
1. Edit `.env` file and set `PORT=5001` (or another port)
2. Or modify `knowledge_hub.py` directly

### Import Errors
If you see import errors:
1. Make sure the virtual environment is activated
2. Run `pip install -r requirements.txt`
3. Verify Python version: `python --version` (should be 3.8+)

### No Answers Returned
- Try rephrasing your question
- Use more specific keywords
- Check the suggested questions for examples

## Future Enhancements

Potential features to add:
- [ ] Integration with external APIs (OpenAI, etc.)
- [ ] User authentication and saved questions
- [ ] Advanced NLP for better question understanding
- [ ] Vector search for semantic matching
- [ ] Admin panel for managing knowledge base
- [ ] Export/import knowledge base
- [ ] Multi-language support
- [ ] Voice input support
- [ ] Chat history
- [ ] Feedback system for answer quality

## License

This project is open source and available for personal and commercial use.

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review the API documentation
3. Check the code comments in `knowledge_hub.py`

---

**Happy learning! 📚**

