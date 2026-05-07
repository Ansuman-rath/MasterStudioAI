# MindStudio AI

<img width="1899" height="863" alt="image" src="https://github.com/user-attachments/assets/c9ee176a-ca5b-472c-8b13-2a0c73744f55" />

> **Empowering Education** — Transforming prompts into personalized learning experiences with AI.

---

## Overview

MindStudio AI is a next-generation AI-powered learning platform that generates comprehensive, structured courses from a single text prompt. Whether you're looking to learn "Quantum Computing" or "Advanced UI Design," the platform leverages Google's Gemini LLM to create multi-day modules, assessments, and downloadable presentations tailored just for you.

## Key Features

- **AI Course Generation**: Instant course outlines (3–18 days) with 3 modules per day.
- **On-Demand Content**: Modules are generated when you need them, ensuring the most relevant information.
- **Smart Search**: Semantic search powered by Pinecone embeddings.
- **Interactive Quizzes**: Assessments built into every module to track your learning.
- **Export to PPT**: Download your lessons as professional PowerPoint presentations.
- **Credit System**: A fair usage system to manage AI resource consumption.

## Tech Stack

- **Frontend**: Next.js 14, Tailwind CSS, Framer Motion
- **Backend**: Next.js API Routes, Prisma
- **AI**: Google Gemini API, Gemini Embeddings
- **Database**: PostgreSQL (Neon)
- **Caching**: Upstash Redis
- **Search**: Pinecone Vector Store

## Getting Started

### Prerequisites

To run MindStudio AI locally, you will need to set up several external services and obtain the following API keys.

| Variable | Service | Description |
| :--- | :--- | :--- |
| `DATABASE_URL` | Neon / PostgreSQL | Main database connection string. |
| `GENAI` | Google AI Studio | API Key for Gemini 3.1 Flash (Generates course content). |
| `PINECONE` | Pinecone | API Key for vector storage (Enables semantic search). |
| `UPSTASH_REDIS_*` | Upstash | Redis URL and Token for content caching. |
| `RESEND_API_KEY` | Resend | For sending transactional emails (Auth). |
| `GOOGLE_CLIENT_*` | Google Cloud | OAuth credentials for Google Login. |
| `AUTH_SECRET` | Auth.js | A random string for session encryption. |

### Local Setup

1. **Clone & Install**:
   ```bash
   bun install
   # or
   npm install
   ```

2. **Environment Configuration**:
   Create a `.env` file in the root directory by copying the example:
   ```bash
   cp .env.example .env
   ```
   Fill in your unique API keys in the `.env` file. **Note: Never share your `.env` file or commit it to version control.**

3. **Database Migration**:
   ```bash
   bun run database
   ```

4. **Run Development Server**:
   ```bash
   bun dev
   ```

## Project Architecture

MindStudio AI follows a modern serverless architecture:
- **Compute**: Next.js Server Components & API Routes.
- **Intelligence**: Google Gemini for content generation and embeddings.
- **Persistence**: Neon PostgreSQL for user data; Pinecone for vector indexing.
- **Performance**: Upstash Redis for caching AI responses.

## License

This project is licensed under the MIT License.
