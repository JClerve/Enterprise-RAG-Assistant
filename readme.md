# 📚 Quiz Generator & Summarizer

> Transform PDFs and YouTube videos into interactive quizzes and comprehensive summaries using advanced AI-powered content processing with multimodal support.

---

## 🚀 Features

### 📄 Content Processing

| Source | Details |
|--------|---------|
| **PDF Upload** | Up to 10MB — text extraction, image detection, OCR for image-heavy documents |
| **YouTube Integration** | Transcript extraction via API, fallback to descriptions, supports all URL formats |
| **Drag & Drop Interface** | Intuitive file upload with drag-and-drop support |

---

### 🤖 AI-Powered Functionality

#### Smart Summarization
- Comprehensive summaries with key points extraction
- Multimodal analysis (text + images for PDFs)
- Structured overviews with main themes
- Support for both text-only and image-rich documents

#### Interactive Quiz Generation
- Multiple-choice questions with customizable parameters
- Context-aware question generation using vector similarity search
- CLIP-based multimodal retrieval for relevant content sections

#### Advanced Content Analysis
- FAISS vector database for similarity search
- CLIP embeddings for text and image understanding
- Semantic chunking and retrieval

---

### 🎯 Quiz Features

**Customizable Configuration**
- Number of questions: 3, 5, 10, 15, or 20
- Difficulty levels: Easy / Medium / Hard with visual indicators
- Specific topic focusing with context-aware generation

**Interactive Experience**
- Real-time progress tracking with animated progress bars
- Instant feedback with correct/incorrect indicators
- Score calculation and performance analytics
- Question review with detailed explanations
- Difficulty badges per question

**Navigation**
- Previous/Next question navigation
- Answer persistence across navigation
- Final results with comprehensive review

---

### 📤 Export & Sharing

- **PDF Export** — Professional formatting and styling
- **Markdown Export** — GitHub Flavored Markdown compatible
- **Plain Text** — Simple sharing format
- **Copy to Clipboard** — One-click quick sharing
- **Summary Statistics** — Word count, character count, and timestamps

---

## 🛠️ Technology Stack

### Frontend

| Tool | Purpose |
|------|---------|
| React 19 | Modern hooks and functional components |
| Vite 7 | Lightning-fast build tool and dev server |
| Tailwind CSS 4 | Utility-first CSS with Vite plugin |
| Lucide React | 530+ icon library |
| React Markdown | GitHub Flavored Markdown rendering |
| Axios | HTTP client for API communication |

### Backend

| Tool | Purpose |
|------|---------|
| FastAPI | Python web framework with auto API docs |
| LangChain 0.2.16 | Document processing and AI chains |
| Groq API (Llama 3.3 70B) | High-performance LLM inference |
| Google Gemini 2.0 Flash | Multimodal AI (image + text) |
| FAISS | Vector database for similarity search |
| HuggingFace Transformers | Embedding models and NLP tools |

### AI/ML Libraries

| Library | Purpose |
|---------|---------|
| OpenAI CLIP | Multimodal text + image embeddings |
| sentence-transformers | Text embedding (all-MiniLM-L6-v2) |
| PyTorch | Deep learning for CLIP inference |
| scikit-learn | Cosine similarity calculations |
| youtube-transcript-api | YouTube transcript extraction |
| yt-dlp | YouTube video info extraction |
| PyMuPDF (fitz) | PDF processing with image extraction |
| Pillow (PIL) | Image processing and format conversion |

---

## 📋 Prerequisites

- **Node.js** v18+
- **Python** v3.8+
- **Groq API Key** — for LLM processing
- **Google API Key** — for Gemini multimodal processing

---

## 🚀 Installation

### Backend Setup

```bash
# 1. Clone the repository
git clone <repository-url>
cd QuizGenerator/Backend

# 2. Create and activate virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment variables
echo "GROQ_API_KEY=your_groq_api_key_here" > .env
echo "GOOGLE_API_KEY=your_google_api_key_here" >> .env

# 5. Start the backend server
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### Frontend Setup

```bash
# 1. Navigate to frontend directory
cd ../Frontend

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev
```

Then open **http://localhost:5173** in your browser.

---

## 🎯 Usage Guide

### Step 1 — Choose Content Source
Select **PDF Document** or **YouTube Video**. Visual icons and descriptions guide your choice.

### Step 2 — Upload Content

**PDF:**
- Drag & drop or browse for a PDF (max 10MB)
- Supports text-heavy, image-rich, and mixed content

**YouTube:**
- Paste a video URL in any supported format:
  ```
  https://www.youtube.com/watch?v=VIDEO_ID
  https://youtu.be/VIDEO_ID
  https://www.youtube.com/embed/VIDEO_ID
  ```

### Step 3 — Configure Action

| Action | What it does |
|--------|-------------|
| **Generate Summary** | Creates a structured overview with key points and topic analysis |
| **Generate Quiz** | Generates 3–20 interactive questions at your chosen difficulty |

### Step 4 — Review Results

- **Summary** — Formatted output with export options (PDF, Markdown, TXT) and statistics
- **Quiz** — Interactive experience with progress tracking, difficulty badges, and navigation
- **Performance** — Score breakdown, correct/incorrect review, and option to retake or start fresh

---

## 📁 Project Structure

```
QuizGenerator/
├── Backend/
│   ├── main.py                        # FastAPI entry point
│   ├── routes/
│   │   ├── summarizeRoutes.py         # Summary generation endpoints
│   │   └── quizRoutes.py              # Quiz generation endpoints
│   ├── controllers/
│   │   ├── summarizeController.py     # Multimodal summarization logic
│   │   └── quizController.py          # CLIP-based retrieval and quiz logic
│   ├── schemas/
│   │   ├── summarySchema.py           # Pydantic models for summaries
│   │   └── quizScehma.py              # Pydantic models for quizzes
│   ├── utils/
│   │   └── helpers.py                 # YouTube extraction utilities
│   └── requirements.txt
│
└── Frontend/
    ├── src/
    │   ├── components/
    │   │   ├── configure/
    │   │   │   ├── ActionSelection.jsx
    │   │   │   └── QuizConfiguration.jsx
    │   │   ├── results/
    │   │   │   ├── QuizComplete.jsx
    │   │   │   ├── QuizQuestion.jsx
    │   │   │   ├── QuizResults.jsx
    │   │   │   └── SummaryResults.jsx
    │   │   ├── upload/
    │   │   │   ├── PDFUpload.jsx
    │   │   │   └── YouTubeUpload.jsx
    │   │   ├── ConfigureAction.jsx
    │   │   ├── ContentTypeSelection.jsx
    │   │   ├── ContentUpload.jsx
    │   │   ├── Results.jsx
    │   │   └── StepIndicator.jsx
    │   ├── api/
    │   │   └── api.js                 # Axios configuration
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── index.css
    ├── package.json
    ├── vite.config.js
    └── index.html
```

---

## 🔧 API Endpoints

### Summary Generation

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/summary/youtube` | Generate summary from YouTube URL |
| `POST` | `/summary/pdf` | Generate multimodal summary from PDF |

### Quiz Generation

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/quiz/youtube` | Generate quiz from YouTube URL |
| `POST` | `/quiz/pdf` | Generate quiz from uploaded PDF |

### Request Schemas

```json
// YouTube Quiz
{ "url": "...", "specificArea": "...", "no": 10, "difficulty": "Medium" }

// PDF Quiz (multipart form)
{ "file": <binary>, "specificArea": "...", "no": 10, "difficulty": "Hard" }

// Quiz Response
[{ "id": 1, "question": "...", "options": [...], "correct": "...", "difficulty": "..." }]
```

---

## 🎨 Advanced Features

**Multimodal Content Processing**
- PyMuPDF-based image extraction from PDFs
- CLIP text and image embeddings for semantic similarity
- FAISS-powered vector retrieval
- Google Gemini for combined image + text understanding

**Smart Quiz Generation**
- Questions sourced from the most relevant content sections
- Color-coded difficulty: 🟢 Easy / 🟡 Medium / 🔴 Hard
- Topic filtering via vector search
- Multiple fallback content extraction strategies

**Enhanced UI/UX**
- Step-by-step wizard with clear progression
- Mobile-first responsive design with Tailwind CSS
- Animated loading states and processing indicators
- Graceful error handling with user feedback

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/AmazingFeature`
3. Commit your changes: `git commit -m 'Add AmazingFeature'`
4. Push to branch: `git push origin feature/AmazingFeature`
5. Open a Pull Request

---

## 📝 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [LangChain](https://langchain.com) — comprehensive document processing
- [Groq](https://groq.com) — high-performance LLM inference
- [Google Gemini](https://deepmind.google/technologies/gemini/) — multimodal AI
- [OpenAI CLIP](https://openai.com/research/clip) — text-image understanding
- [Tailwind CSS](https://tailwindcss.com) — responsive UI framework
- [FastAPI](https://fastapi.tiangolo.com) — robust API development
- [FAISS](https://faiss.ai) — efficient vector similarity search
