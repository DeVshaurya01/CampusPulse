# CampusPulse

CampusPulse is a modern, AI-powered platform designed to automatically extract and manage campus event details.

## Key Features

- **AI-Powered Event Extraction**: Automatically extracts important event details using the **Groq API** (implemented by Soumik).
- **Authentication**: Secure user login via **Email and Password**, powered by Supabase Auth (bypassing traditional email constraints).
- **Admin Dashboard**: A comprehensive moderation interface to manage events.
- **Database**: Robust data management with Supabase.

## Getting Started

First, ensure you have your environment variables set up (refer to `.env.example`):

```bash
cp .env.example .env.local
```

Then, install the dependencies and run the development server:

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Tech Stack

- **Framework**: [Next.js](https://nextjs.org/)
- **Backend & Auth**: [Supabase](https://supabase.com/)
- **AI Engine**: [Groq API](https://groq.com/)
- **Styling**: Tailwind CSS
