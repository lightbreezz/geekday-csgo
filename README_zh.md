# 潮韵同行 (CSGO)

**Slogan**: Match Fast, Think Less, Remember Smart.

**潮韵同行 (CSGO)** 是一个专为潮汕地区设计的深度客制化动态文旅 Agent。它是一个懂“潮式生活”的智能体，基于开源模型，内置“天气 + 爱好 + 人流量”的动态规划公式，并深度融合了文化规则。

## 🚀 核心功能

- **动态规划引擎**：创新性建立实时决策公式：`推荐结果 = f(实时天气, 用户爱好, 区域人流量, 交通状况)`。拒绝静态死板的列表推荐，根据环境变化实时调整行程。
- **推荐引擎**：提供开箱即用的模版，让用户能够快速定义自己的兴趣偏好。
- **分层记忆系统**：
  - **短期记忆**：处理当前对话上下文。
  - **中期记忆**：缓存已确认的行程草案。
  - **长期记忆**：持久化用户的饮食偏好（如“不吃香菜”），实现“越用越懂你”。

## 🛠️ 技术栈

### 后端 (Backend)
- **语言**：Python 3.11+
- **框架**：FastAPI
- **AI/智能体**：LangGraph, LangChain Core
- **LLM 集成**：OpenAI SDK (兼容 SophNet/Qwen)
- **协议**：MCP (Model Context Protocol)

### 前端 (Frontend)
- **框架**：Vue 3
- **语言**：TypeScript
- **构建工具**：Vite
- **样式**：CSS Variables (主题化)

## 📦 安装与设置

### 前置要求
- Docker & Docker Compose (推荐)
- 或者 Python 3.11+ 和 Node.js 20+

### 选项 1：使用 Docker Compose (推荐)

1. 克隆代码库。
   ```bash
   git clone https://github.com/lightbreezz/geekday-csgo.git
   cd geekday-csgo
   ```

2. 在根目录下创建一个 `.env` 文件（如果有 `.env.example` 可以复制一份），并配置你的 API 密钥。
   ```ini
   SOPHNET_API_KEY=sk-xxxxxxxxxxxx
   SOPHNET_BASE_URL=https://www.sophnet.com/api/open-apis/v1
   USE_MOCK_DATA=True  # 设置为 True 以使用模拟数据（无需 Key）
   ```

3. 运行应用程序：
   ```bash
   docker-compose up --build
   ```

- **后端**：http://localhost:8000
- **前端**：http://localhost:5173

### 选项 2：手动设置

#### 后端

1. 进入后端目录：
   ```bash
   cd backend
   ```

2. 安装依赖：
   ```bash
   pip install -e .
   ```

3. 配置环境变量（创建 `.env`）：
   ```ini
   SOPHNET_API_KEY=your_api_key
   SOPHNET_BASE_URL=https://www.sophnet.com/api/open-apis/v1
   USE_MOCK_DATA=True
   ```

4. 启动服务器：
   ```bash
   uvicorn app.main:app --reload
   ```

#### 前端

1. 进入前端目录：
   ```bash
   cd frontend
   ```

2. 安装依赖：
   ```bash
   npm install
   ```

3. 启动开发服务器：
   ```bash
   npm run dev
   ```

## 📂 项目结构

```
.
├── backend/                # Python FastAPI 后端
│   ├── app/
│   │   ├── agent/          # AI 智能体逻辑与工具
│   │   ├── api/            # API 路由
│   │   ├── core/           # 配置
│   │   ├── services/       # 业务逻辑服务
│   │   └── main.py         # 应用程序入口
│   └── pyproject.toml      # Python 依赖
├── frontend/               # Vue.js 前端
│   ├── src/
│   │   ├── api/            # API 客户端
│   │   ├── components/     # Vue 组件
│   │   ├── views/          # 页面视图
│   │   └── main.ts         # 前端入口
│   └── package.json        # Node.js 依赖
└── docker-compose.yml      # Docker 编排
```

## 📄 许可证

[MIT License](LICENSE)
