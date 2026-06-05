# 🎓 CampusPulse

**🌐 Live Demo:** [https://campuspulse-jade.vercel.app](https://campuspulse-jade.vercel.app)

CampusPulse is a modern, dynamic, and fully-featured campus event discovery and management platform. Powered by AI, it automatically extracts and parses important details from event posters or descriptions, allowing students to effortlessly track, share, and RSVP to campus activities.

---

## 🚀 Key Features

*   **🤖 AI-Powered Event Extraction:** Effortlessly parse event details (like date, time, venue, and descriptions) utilizing the **Groq API** (implemented by Soumik).
*   **🔐 Secure Authentication:** Seamless and secure user login utilizing **Supabase Email and Password Authentication**, purposely designed to bypass standard email delivery constraints.
*   **📅 Interactive Calendars:** A beautiful, responsive event calendar integrated with `@fullcalendar/react` for easy visualization of your schedule.
*   **👥 Community Feed & Interactions:** Users can post to the community feed, vote on trending activities, and interact with events (RSVP as "Going", "Interested", or "Star" them).
*   **🛡️ Admin Moderation Dashboard:** Built-in dashboard to oversee events and moderate community interactions.

---

## 🛠️ Tech Stack

This project is built on a highly scalable modern web stack:

**Frontend Ecosystem**
*   **Framework:** [Next.js 14](https://nextjs.org/) (App Router)
*   **Library:** React 18
*   **Styling:** [Tailwind CSS](https://tailwindcss.com/)
*   **Icons:** [Lucide React](https://lucide.dev/)
*   **Calendar:** [FullCalendar](https://fullcalendar.io/)
*   **Date Formatting:** `date-fns`

**Backend & Database**
*   **Database:** [Supabase](https://supabase.com/) (PostgreSQL)
*   **Authentication:** Supabase Auth
*   **Security:** Row Level Security (RLS) enabled on all tables

**AI & Machine Learning**
*   **Primary AI Engine:** [Groq API](https://groq.com/) (`groq-sdk`)
*   **Fallback/Vision AI:** Google Generative AI (`@google/generative-ai`)

---

## 🗄️ Database Architecture

The backend operates on a fully relational PostgreSQL database hosted on Supabase.
Check `schema.sql` for the complete schema.

1.  **`events`**: Core table storing AI-extracted event data (title, date, venue, category).
2.  **`posts`**: Community discussions and trending feed items linked to specific events.
3.  **`user_interactions`**: A join table tracking unique user RSVPs (`going`, `interested`, `star`) linked securely to their Supabase User ID.

---

## 🏗️ Project Structure

```text
campuspulse/
├── public/                 # Static assets
├── src/
│   ├── app/                # Next.js App Router (pages & layouts)
│   ├── components/         # Reusable React UI components
│   ├── lib/                # Utility scripts, Supabase/Groq client setup
│   └── types.ts            # Global TypeScript definitions
├── schema.sql              # Supabase database initialization script
└── tailwind.config.ts      # Tailwind CSS styling tokens
```

---

## 💻 Getting Started

Follow these instructions to set up the project locally.

### 1. Clone the repository and install dependencies

```bash
git clone https://github.com/DeVshaurya01/CampusPulse.git
cd CampusPulse
npm install
```

### 2. Configure Environment Variables

Create a `.env.local` file in the root directory and add the required API keys (refer to `.env.example`):

```bash
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# AI Extraction (Groq)
GROQ_API_KEY=your_groq_api_key_here
```

### 3. Database Setup

1.  Create a new [Supabase](https://supabase.com/) project.
2.  Navigate to the Supabase SQL Editor.
3.  Copy and run the contents of `schema.sql` to generate the required tables, set up Realtime features, and enforce Row Level Security (RLS).

### 4. Run the Development Server

Start up your local Next.js environment:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see CampusPulse in action!

---

## 👥 Contributors
*   **DeVshaurya01** - Project Architecture, Frontend, Auth & Database setup
*   **Soumik** - AI Event Extraction Integration (Groq API)
