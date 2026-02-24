# CSGO - Frontend

This directory contains the frontend application for the CSGO platform.

## 🛠️ Tech Stack

- **Framework**: Vue 3
- **Language**: TypeScript
- **Build Tool**: Vite
- **Styling**: CSS Variables (Theming)

## 📂 Structure

- `src/`: Source code
  - `api/`: API client and services
  - `components/`: Vue components
  - `views/`: Page views
  - `router/`: Vue Router configuration
  - `data/`: Static data (e.g., spots)
  - `styles/`: Global styles and tokens
- `public/`: Static assets

## 🚀 Getting Started

### Prerequisites

- Node.js 20+
- npm

### Installation

1. Navigate to this directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

   The application will be available at `http://localhost:5173`.

## 📦 Build

To build the application for production:

```bash
npm run build
```

The output will be in the `dist/` directory.
