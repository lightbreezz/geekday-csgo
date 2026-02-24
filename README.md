# 潮韵同行 (CSGO)

**Slogan**: Match Fast, Think Less, Remember Smart.

**潮韵同行 (CSGO)** is a deeply customized dynamic cultural tourism agent designed for the Chaoshan region. It is an intelligent agent that understands "Chaoshan lifestyle". Based on open-source models, it incorporates a dynamic planning formula of "Weather + Hobbies + Crowd Density" and deeply integrates cultural rules. 

## 🚀 Features
- **Dynamic Planning Engine**: innovative real-time decision formula: `Recommendation = f(Real-time Weather, User Hobbies, Crowd Density, Traffic)`. It rejects static lists and adjusts itineraries dynamically.
- **Recommendation Engine**: features ready-to-use templates that allow users to quickly define their interests.
- **Hierarchical Memory**:
  - **Short-term**: Contextual dialogue.
  - **Mid-term**: Confirmed itinerary drafts.
  - **Long-term**: User preferences (e.g., dietary restrictions).

## 🛠️ Tech Stack

### Backend
- **Language**: Python 3.11+
- **Framework**: FastAPI
- **AI/Agents**: LangGraph, LangChain Core
- **LLM Integration**: OpenAI SDK (Compatible with SophNet/Qwen)
- **Protocol**: MCP (Model Context Protocol)

### Frontend
- **Framework**: Vue 3
- **Language**: TypeScript
- **Build Tool**: Vite
- **Styling**: CSS Variables (Theming)

## 📦 Installation & Setup

### Prerequisites
- Docker & Docker Compose (Recommended)
- OR Python 3.11+ and Node.js 20+

### Option 1: Using Docker Compose (Recommended)

1. Clone the repository.
   ```bash
   git clone https://github.com/lightbreezz/geekday-csgo.git
   cd geekday-csgo
   ```

2. Create a `.env` file in the root directory (copy from `.env.example`) and configure your API keys.
   ```ini
   SOPHNET_API_KEY=sk-xxxxxxxxxxxx
   SOPHNET_BASE_URL=https://www.sophnet.com/api/open-apis/v1
   USE_MOCK_DATA=True  # Set to True to use mock data if you don't have keys
   ```

3. Run the application:
   ```bash
   docker-compose up --build
   ```

- **Backend**: http://localhost:8000
- **Frontend**: http://localhost:5173

### Option 2: Manual Setup

#### Backend

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   pip install -e .
   ```

3. Configure environment variables (create `.env`):
   ```ini
   SOPHNET_API_KEY=your_api_key
   SOPHNET_BASE_URL=https://www.sophnet.com/api/open-apis/v1
   USE_MOCK_DATA=True
   ```

4. Start the server:
   ```bash
   uvicorn app.main:app --reload
   ```

#### Frontend

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

## 🔌 Integration (OpenClaw / MCP)

The project includes resources for integrating with external AI agent platforms like **OpenClaw** or **OpenAI GPTs**.

- **OpenAPI Specification**: See [`backend/docs/openclaw/openapi.json`](backend/docs/openclaw/openapi.json)
- **Integration Guide**: See [`backend/docs/openclaw/README.md`](backend/docs/openclaw/README.md)
- **Trae Skill**: Located at `.trae/skills/chaoshan-travel/SKILL.md`

## 📂 Project Structure

```
.
├── backend/                # Python FastAPI Backend
│   ├── app/
│   │   ├── agent/          # AI Agent logic & Tools
│   │   ├── api/            # API Routes
│   │   ├── core/           # Configuration
│   │   ├── services/       # Business Logic Services
│   │   └── main.py         # Application Entry Point
│   └── pyproject.toml      # Python Dependencies
├── frontend/               # Vue.js Frontend
│   ├── src/
│   │   ├── api/            # API Client
│   │   ├── components/     # Vue Components
│   │   ├── views/          # Page Views
│   │   └── main.ts         # Frontend Entry Point
│   └── package.json        # Node.js Dependencies
└── docker-compose.yml      # Docker Orchestration
```

## 📄 License

[MIT License](LICENSE)
