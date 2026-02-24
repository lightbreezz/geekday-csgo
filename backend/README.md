# CSGO - Backend

This directory contains the backend services for the CSGO platform.

## 🛠️ Tech Stack

- **Framework**: FastAPI
- **Language**: Python 3.11+
- **AI/Agents**: LangGraph, LangChain Core
- **LLM Integration**: OpenAI SDK (Compatible with SophNet/Qwen)
- **Protocol**: MCP (Model Context Protocol)

## 📂 Structure

- `app/`: Main application package
  - `agent/`: AI Agent logic and tools
  - `api/`: API route definitions
  - `core/`: Configuration and core utilities
  - `services/`: Business logic services (LLM, MCP, Memory)
  - `schemas/`: Pydantic models for request/response
  - `memory/`: JSON-based memory storage
- `main.py`: Application entry point

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- pip

### Installation

1. Navigate to this directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   pip install -e .
   ```

3. Configure environment variables. Create a `.env` file (or use the one in the root directory):
   ```ini
   SOPHNET_API_KEY=your_api_key
   SOPHNET_BASE_URL=https://www.sophnet.com/api/open-apis/v1
   USE_MOCK_DATA=True
   ```

4. Run the server:
   ```bash
   uvicorn app.main:app --reload
   ```

## 🧪 Testing

(Add testing instructions here if applicable)
