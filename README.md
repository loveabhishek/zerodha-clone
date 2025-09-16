# Zerodha-Clone

> A simple, responsive stock-trading UI clone inspired by Zerodha Kite — built for learning and portfolio demonstration. This repository contains both **frontend** and **backend** parts so you can run the full-stack app locally and deploy it.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Live Demo / Screenshots](#live-demo--screenshots)
3. [Features](#features)
4. [Tech Stack](#tech-stack)
5. [Repository Structure](#repository-structure)
6. [Prerequisites](#prerequisites)
7. [Getting Started (Local Development)](#getting-started-local-development)

   * [Frontend](#frontend)
   * [Backend](#backend)
8. [Environment Variables](#environment-variables)
9. [Scripts](#scripts)
10. [Deployment](#deployment)
11. [Testing](#testing)
12. [Assets & Images](#assets--images)
13. [Contributing](#contributing)
14. [License](#license)
15. [Contact](#contact)

---

## Project Overview

This project is a learning-focused clone of the Zerodha Kite UI. It recreates core UI flows such as market watch, order placement UI, charts, portfolio and a sample dashboard. **Important:** This is a mock / demo app — it does **not** connect to any real brokerage or place real trades.

Use this project to practice React, component design, state management, routing, authentication flows, and connecting a frontend to a simple backend API.

## Live Demo / Screenshots

*(Add your deployment link or screenshots here)*

* Live demo: `https://your-frontend-hosting.example` (replace with your deployed URL)
* Screenshots: `./docs/screenshots/` (add images of the UI)

## Features

* Responsive trading-dashboard-like UI
* Market watch list with mock data
* Stock details page with chart placeholder
* Place mock buy/sell orders (client-side simulated)
* Portfolio / holdings page
* Simple user authentication (mock JWT/session)
* Admin / dashboard view (optional)

## Tech Stack

* Frontend: React (Create React App / Vite), React Router, Hooks, Context or Redux (optional)
* Styling: CSS / SCSS / Tailwind (your choice)
* Backend: Node.js + Express (or your preferred stack)
* Database: MongoDB (local or Atlas) or a simple JSON file for mock data
* Charts: Chart.js / Recharts (optional)

## Repository Structure

```
zerodha-clone/
├─ frontend/                # React app
│  ├─ public/
│  ├─ src/
│  │  ├─ components/
│  │  ├─ pages/
│  │  ├─ services/          # API calls
│  │  ├─ assets/            # images, icons
│  │  ├─ App.js
│  │  └─ index.js
│  └─ package.json
├─ backend/                 # Express API
│  ├─ controllers/
│  ├─ routes/
│  ├─ models/
│  ├─ seed/                 # mock data seeders
│  ├─ server.js
│  └─ package.json
├─ docs/
│  └─ screenshots/
├─ .gitignore
└─ README.md
```

## Prerequisites

* Node.js (v14+ recommended)
* npm or yarn
* MongoDB (if using a real DB) or use a hosted MongoDB Atlas cluster

## Getting Started (Local Development)

> Clone the repo, then run frontend and backend separately.

```bash
# 1. clone
git clone https://github.com/<your-username>/zerodha-clone.git
cd zerodha-clone
```

### Frontend

```bash
cd frontend
# install deps
npm install
# env file (see Environment Variables below)
cp .env.example .env
# run dev server
npm start
# or if using yarn
# yarn
# yarn start
```

Open `http://localhost:3000` in your browser.

### Backend

```bash
cd backend
npm install
# env file (see Environment Variables below)
cp .env.example .env
# start server (dev)
npm run dev     # if using nodemon
# or
node server.js
```

Default backend port used in code: `http://localhost:5000` (adjust if you changed it).

## Environment Variables

Create `.env` files for frontend and backend. Example variables:

### frontend/.env

```
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_GOOGLE_MAPS_KEY=your_key_if_needed
```

### backend/.env

```
PORT=5000
MONGO_URI=mongodb://localhost:27017/zerodha_clone
JWT_SECRET=your_jwt_secret_here
```

## Scripts

Common scripts you might include in each package.json:

**Frontend**

```json
"scripts": {
  "start": "react-scripts start",
  "build": "react-scripts build",
  "test": "react-scripts test",
  "eject": "react-scripts eject"
}
```

**Backend**

```json
"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js",
  "seed": "node seed/seed.js"
}
```

## Deployment

You can deploy frontend and backend separately:

* Frontend: Vercel / Netlify / GitHub Pages (build output from `npm run build`)
* Backend: Heroku / Railway / Render / DigitalOcean App Platform
* MongoDB: MongoDB Atlas (cloud) or managed DB from your provider

When deploying, update `REACT_APP_API_URL` to point to your deployed backend URL.

## Testing

Add unit & integration tests as you build features. Example choices:

* Frontend: Jest + React Testing Library
* Backend: Jest + Supertest

## Assets & Images

Keep all images used in the frontend inside `frontend/src/assets/` and load them via relative imports. If images are missing when running locally, verify:

1. Files are actually present in the `assets` folder.
2. Import/paths match exactly (case-sensitive on some systems).
3. If bundler can't find images, move them to `public/` and reference with `/assets/...`.

## Common Troubleshooting

* **Module not found: react-router-dom** — install the package in `frontend`: `npm install react-router-dom@6` (or the version your app expects).
* **Images not showing** — check the import paths and ensure files were added to Git (not only locally).
* **CORS errors** — allow CORS in backend for dev: `npm install cors` and `app.use(cors());` in Express.
* **Port conflicts** — change ports in `.env` files.

## Contributing

Contributions are welcome. Suggested workflow:

1. Fork the repo
2. Create a feature branch `git checkout -b feat/your-feature`
3. Commit changes `git commit -m "feat: add ..."`
4. Push and make a
