# Gestion PFA — Frontend

A React-based web interface for the academic project management platform **Gestion PFA**. It provides dedicated dashboards and tools for students, professors, and administrators to manage the PFA process.

## Features

- **Role-based interfaces** — Dedicated interfaces for students, professors, and administrators.
- **Authentication** — Login, registration, password recovery, and password reset interfaces.
- **Project management** — Browse topics, submit topic requests, and manage topic selection.
- **Supervision management** — Manage professor availability, student-supervisor assignments, and team formation.
- **Scheduling** — Calendar-based availability management and defense scheduling.
- **Dashboards & statistics** — Visual dashboards, statistics, and project progress tracking.
- **Notifications** — Interface for notifications and updates.
- **Chat interface** — Communication interface between users.
- **Results management** — View defense results and related information.

## Tech Stack

- **React 18** — Component-based UI development.
- **Vite 5** — Development server and build tool.
- **React Router** — Client-side routing.
- **Axios** — HTTP requests and API communication.
- **FullCalendar** — Calendar and scheduling interfaces.
- **Lucide React** — Icons.
- **Tailwind CSS** — Utility-first CSS framework.

## Getting Started

### Prerequisites

- Node.js
- npm

### Installation

```bash
git clone https://github.com/omrani-wiem/Gestion_pfa.git
cd Gestion_pfa/frontend
npm install
```

### Development

Start the development server:

```bash
npm run dev
```

The application will be available at the URL displayed in your terminal (usually `http://localhost:5173`).

### Production Build

Build the application for production:

```bash
npm run build
```

Preview the production build:

```bash
npm run preview
```

## Project Structure

```text
frontend/
├── src/
│   ├── api/           # API configuration and HTTP clients
│   ├── Components/    # UI components and dashboards
│   ├── guards/       # Role-based route protection
│   ├── nav/          # Navigation configurations by role
│   ├── App.jsx       # Main application component
│   ├── main.jsx     # Application entry point
│   └── index.css    # Global styles
├── index.html
├── vite.config.js
└── package.json
```

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Build the application |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint |

---

*Frontend developed as part of the Gestion PFA academic project.*
