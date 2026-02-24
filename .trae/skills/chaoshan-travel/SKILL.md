---
name: "chaoshan-travel"
description: "Helps users plan trips to Chaoshan, check weather, and understand local culture by interacting with the Chaoyun Yunnao API. Invoke when user asks about Chaoshan travel, itinerary planning, or local customs."
---

# Chaoshan Travel Planner Skill

This skill allows the AI to interact with the **Chaoyun Yunnao (CSGO)** backend to provide travel planning services for the Chaoshan region.

## Prerequisites

1.  **Backend Server**: The backend server must be running on port `8000`.
    -   Check status: `curl -I http://localhost:8000/docs`
    -   Start server (Docker): `docker-compose up -d backend`
    -   Start server (Manual): `cd backend && uvicorn app.main:app --reload --port 8000`

## Capabilities

### 1. Plan a Trip
Generate a personalized itinerary based on user preferences.

-   **Endpoint**: `POST http://localhost:8000/api/v1/plan`
-   **Payload**:
    ```json
    {
      "days": 2,
      "preferences": ["food", "culture"],
      "companion": "friends"
    }
    ```
-   **Usage**:
    When a user asks to plan a trip (e.g., "Plan a 2-day food trip to Chaoshan"), construct the payload and call this endpoint.

### 2. Chat with Agent
Ask questions about local culture, food, or specific spots.

-   **Endpoint**: `POST http://localhost:8000/api/v1/chat`
-   **Payload**:
    ```json
    {
      "message": "What is beef hotpot?",
      "history": []
    }
    ```
-   **Usage**:
    When a user asks a specific question about Chaoshan (e.g., "Tell me about Naore"), use this endpoint to get an answer from the domain-specific agent.

### 3. Check Weather
Get real-time or forecasted weather for a city in Chaoshan.

-   **Endpoint**: `GET http://localhost:8000/api/v1/weather?city=Shantou&days=3`
-   **Usage**:
    Invoke when the user asks about the weather.

## Example Workflow

1.  **User**: "Plan a weekend trip to Shantou for food."
2.  **AI**:
    -   Check if backend is running.
    -   Call `POST /api/v1/plan` with `{"days": 2, "preferences": ["food"], "companion": "friends"}`.
    -   Present the returned itinerary to the user.
