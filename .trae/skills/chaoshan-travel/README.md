# 潮韵同行 (CSGO) Skill 使用指南

本指南将教你如何在 Trae IDE 或其他支持 AI Agent 的环境中使用 **Chaoshan Travel Skill**，让 AI 能够直接为你规划潮汕行程、查询天气和解答文化问题。

## 🛠️ 前置条件

在使用 Skill 之前，**必须**确保本地后端服务正在运行，因为 Skill 需要调用本地 API。

1.  **检查服务状态**：
    在终端运行以下命令，如果返回 `HTTP/1.1 200 OK` 说明服务正常。
    ```bash
    curl -I http://localhost:8000/docs
    ```

2.  **启动服务**（如果未运行）：
    *   **Docker 方式 (推荐)**：
        ```bash
        docker-compose up -d backend
        ```
    *   **手动方式**：
        ```bash
        cd backend
        uvicorn app.main:app --reload --port 8000
        ```

## 🚀 如何触发 Skill

在 Trae IDE 的对话框中，你可以直接用自然语言与 AI 交互。Skill 会根据你的意图自动触发。

### 场景 1：行程规划 (Plan a Trip)

告诉 AI 你的旅行偏好，它会调用后端生成个性化行程。

*   **用户指令示例**：
    > "帮我规划一个周末去汕头的行程，我想吃牛肉火锅和看历史建筑。"
    > "Plan a 2-day trip to Chaoshan for food lovers."

*   **Skill 动作**：
    AI 会调用 `POST /api/v1/plan` 接口，参数可能如下：
    ```json
    {
      "days": 2,
      "preferences": ["美食", "历史"],
      "destination": "汕头"
    }
    ```

### 场景 2：文化问答 (Chat with Agent)

询问关于潮汕文化的具体问题，AI 会调用专用的文化 Agent 进行解答。

*   **用户指令示例**：
    > "什么是‘营老爷’？"
    > "介绍一下潮汕工夫茶的礼仪。"

*   **Skill 动作**：
    AI 会调用 `POST /api/v1/chat` 接口，获取专业的文化知识解答。

### 场景 3：天气查询 (Check Weather)

询问天气情况，AI 会获取实时数据。

*   **用户指令示例**：
    > "明天潮州天气怎么样？"
    > "Check the weather in Shantou for the next 3 days."

*   **Skill 动作**：
    AI 会调用 `GET /api/v1/weather` 接口。

## 🔌 集成到其他平台 (OpenClaw / GPTs)

如果你想在 OpenClaw 或自定义 GPTs 中使用此能力，请参考以下资源：

*   **OpenAPI 规范**：[`backend/docs/openclaw/openapi.json`](../../backend/docs/openclaw/openapi.json)
    *   直接导入此 JSON 文件即可让其他 Agent 平台理解 API 结构。
*   **MCP 服务**：[`backend/app/services/mcp_server.py`](../../backend/app/services/mcp_server.py)
    *   支持 Model Context Protocol (MCP) 的平台可以直接连接此服务。

## ❓ 常见问题

**Q: AI 提示 "Failed to connect to backend"？**
A: 请检查 Docker 容器是否运行正常，或者 `localhost:8000` 是否被占用。

**Q: 规划的行程不够个性化？**
A: 尝试提供更详细的指令，例如明确说明人数、预算和具体的兴趣点（如“摄影”、“探店”）。
