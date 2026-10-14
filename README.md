<div align="center">

<img src="https://github.com/user-attachments/assets/69b7187d-7d8c-4c7a-bd76-661b1d0092fe" alt="Rhythm Logo" width="80" />

# Rhythm

### A premium video-sharing platform — Netflix-grade UI, Firebase backend, zero server cost.

[![React](https://img.shields.io/badge/React-18-61dafb?style=flat-square&logo=react)](https://reactjs.org)
[![Vite](https://img.shields.io/badge/Vite-4-646cff?style=flat-square&logo=vite)](https://vitejs.dev)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-38bdf8?style=flat-square&logo=tailwindcss)](https://tailwindcss.com)
[![Firebase](https://img.shields.io/badge/Firebase-10-ffca28?style=flat-square&logo=firebase)](https://firebase.google.com)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-10-ff0055?style=flat-square&logo=framer)](https://www.framer.com/motion)
[![License: MIT](https://img.shields.io/badge/License-MIT-white?style=flat-square)](LICENSE)

[Live Demo](https://rhythm-5cfc5.web.app) · [Report Bug](https://github.com/digvijay-shingare/rhythm/issues) · [Request Feature](https://github.com/digvijay-shingare/rhythm/issues)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Screenshots](#screenshots)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Firebase Setup](#firebase-setup)
  - [Running Locally](#running-locally)
- [Project Structure](#project-structure)
- [Core Features Deep Dive](#core-features-deep-dive)
  - [Video Player](#video-player)
  - [Dynamic Genre System](#dynamic-genre-system)
  - [User Dashboard](#user-dashboard)
  - [Admin Panel](#admin-panel)
  - [Font System](#font-system)
- [Deployment](#deployment)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

**Rhythm** is a full-stack video blog platform built with a focus on premium user experience. Inspired by the design language of Netflix and modern streaming services, it delivers cinematic UI animations, a fully functional admin control panel, per-user analytics dashboards, dynamic genre tagging, and a custom video player — all serverless on Firebase.

The project started as a Create React App and was entirely re-engineered with **Vite**, **Tailwind CSS**, **Zustand**, and **Framer Motion** to achieve a production-grade, performance-first architecture.

---

## Screenshots

### Homepage — Cinematic Hero + Auto-scrolling Carousels

![Homepage Hero](https://github.com/user-attachments/assets/36fe9540-bef8-40a3-b5d5-90e107a7fda8)

### Category Browse — Paginated Grid View

![Category Browse](https://github.com/user-attachments/assets/5a4e9878-3a9f-41a3-aa99-68140317c954)

### User Profile — Custom Banner + Stats

![User Profile](https://github.com/user-attachments/assets/c25a8488-67e2-4611-9680-77a3f4c95e7c)

### Create Post — Genre Autocomplete + Quality & Subtitle Upload

![Create Post](https://github.com/user-attachments/assets/f7f3b4df-ce91-41dd-a0ca-8b737703e41c)

### User Dashboard — Overview

![Dashboard Overview](https://github.com/user-attachments/assets/a292fdac-e68c-4c61-897b-e363d7a29dfb)

### User Dashboard — Analytics (Recharts)

![Dashboard Analytics](https://github.com/user-attachments/assets/cfa4e94b-5638-4088-9d40-319264bd70cb)

### User Dashboard — My Posts

![Dashboard Posts](https://github.com/user-attachments/assets/27cf46d2-7237-4bd7-b2df-5ec83c1b88a4)

### Mobile View

![Mobile Home](https://github.com/user-attachments/assets/697dfe82-7517-419b-b7c4-ee39b165125b)

---

## Features

### Platform

- **Cinematic hero section** — auto-plays the latest or admin-featured video with animated text entrance and mute toggle
- **Horizontal category carousels** with slow auto-scroll (0.5px/frame), pause-on-hover, ping-pong direction reversal, and manual navigation arrows
- **Paginated grid view** when browsing a category — 20 videos per page with animated page transitions
- **Real-time search** across video titles, categories, and locations
- **Dynamic genre system** — 90 globally recognised genres with searchable autocomplete and validation on upload
- **Google OAuth** sign-in — zero password management, session persisted via Zustand + localStorage

### Video Experience

- Custom-built video player on top of `react-player` with full custom control overlay
- **Quality selector** — tag quality on upload (360p → 4K), change playback quality hint during viewing
- **Subtitle support** — upload WebVTT (.vtt) files, CC toggle in the player controls and settings gear
- Controls auto-hide after 3 seconds during playback, reveal on mouse move or touch
- Hover-to-preview on all video cards with smooth scale + glow animation

### User Dashboard

| Section | What it shows |
|---|---|
| Overview | Stat tiles (posts, views, likes, favourites) + recent posts grid |
| My Posts | Full CRUD list with per-post view/like counts and delete |
| Favourites | Saved videos with one-click remove |
| Analytics | Bar chart (views per post), area chart (likes per post), engagement rate % |
| Settings | Avatar upload, profile banner upload, bio, display name, font family selector |

### Admin Panel (`/admin`)

Role-gated — only Firestore users with `role: "admin"` can access.

| Section | Capabilities |
|---|---|
| Overview | Platform KPIs + recent upload activity feed |
| Analytics | Category donut chart, top videos by views bar chart |
| Users | Sortable table, promote/demote admin, delete users |
| Content | All videos, feature toggle (sets hero video), delete |
| Settings | Site name, accent colour, font family, upload size limit, maintenance mode |
| Storage | Used vs available donut, per-user storage breakdown |
| Audit Log | Ready for Cloud Functions deployment |

### Design System

- Dark-first design (`#07070f` base, `#e50914` cinematic red accent)
- 8 switchable Google Fonts with live preview — Inter, Poppins, Manrope, DM Sans, Plus Jakarta Sans, Outfit, Raleway, Nunito
- Font change applies to the entire app in real-time and is persisted to Firestore
- Framer Motion animations throughout — page transitions, staggered card entrances, spring-animated sidebars, hero text stagger
- Fully responsive — 320px mobile through 2XL desktop

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React 18 |
| Build tool | Vite 4 |
| Styling | Tailwind CSS v3 with custom design tokens |
| Animation | Framer Motion v10 |
| State management | Zustand v4 with `persist` middleware |
| Database | Firebase Firestore |
| File storage | Firebase Storage |
| Authentication | Firebase Auth (Google OAuth) |
| Hosting | Firebase Hosting |
| Charts | Recharts v2 |
| Video player | react-player v2 |
| Markdown editor | @uiw/react-md-editor |
| Markdown renderer | react-markdown + remark-gfm |
| Routing | React Router DOM v6 |
| Dates | date-fns |
| Toasts | react-hot-toast |
| Icons | react-icons (Ionicons 5, Material) |

---

## Getting Started

### Prerequisites

- Node.js >= 18
- A Firebase project with **Firestore**, **Storage**, and **Authentication** (Google provider) enabled

### Installation

```bash
git clone https://github.com/digvijay-shingare/rhythm.git
cd rhythm
npm install
```

### Firebase Setup

Replace the Firebase config in `src/lib/firebase.js` with your own project credentials from the Firebase Console:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID",
};
```

**Creating the first Admin user**

After signing in with Google for the first time, open Firebase Console → Firestore → `users/{your-uid}` and manually set:

```json
{ "role": "admin" }
```

All subsequent admin promotions can be done directly from the Admin Panel UI at `/admin`.

### Running Locally

```bash
npm start          # Vite dev server → http://localhost:3000
npm run build      # Production build → ./build
npm run preview    # Preview production build locally
```

---

## Project Structure

```
src/
├── App.jsx                     # Root router, auth guards, settings loader
├── index.jsx                   # ReactDOM entry, Toaster provider
│
├── Components/                 # Reusable UI components
│   ├── NavBar.jsx              # Scroll-aware glass nav (transparent → solid)
│   ├── CategoryBar.jsx         # Dynamic category pills (Firestore-driven)
│   ├── Feed.jsx                # Hero + carousels (home) or paginated grid (category)
│   ├── HeroSection.jsx         # Fullscreen autoplay hero with animated text entrance
│   ├── VideoCarousel.jsx       # Auto-scrolling horizontal row
│   ├── VideoCard.jsx           # Hover-to-preview card with info overlay
│   ├── VideoPinDetail.jsx      # Full player page — quality selector + CC subtitles
│   ├── Create.jsx              # Upload form — genre autocomplete + VTT upload
│   ├── UserProfile.jsx         # Public profile with banner, stats, video grid
│   ├── Search.jsx              # Live search results grid
│   ├── UserAvatar.jsx          # Avatar with referrerPolicy fix + error fallback
│   └── SkeletonCard.jsx        # Shimmer loading placeholders
│
├── Container/                  # Route-level page containers
│   ├── Home.jsx                # Main app shell (NavBar + CategoryBar + Routes)
│   ├── Login.jsx               # Google OAuth login — restores original URL after login
│   ├── Error.jsx               # 404 page
│   ├── AdminLayout.jsx         # Admin shell with spring-animated mobile sidebar
│   ├── DashboardLayout.jsx     # User dashboard shell with spring-animated mobile sidebar
│   ├── admin/                  # Admin panel panels
│   └── dashboard/              # User dashboard panels
│
├── store/
│   ├── useAuthStore.js         # User, role, accessToken, hydration flag
│   ├── useAppSettingsStore.js  # Site-wide settings from Firestore
│   └── usePlayerStore.js       # Video player state
│
├── lib/
│   ├── firebase.js             # Firebase app, db, storage, auth instances
│   ├── firestore/              # Firestore query modules (videos, users, settings)
│   └── utils/
│       ├── formatters.js       # timeAgo, formatNumber, formatDuration, formatBytes
│       └── fonts.js            # Google Fonts dynamic injection
│
├── hooks/
│   ├── useScrolled.js          # Scroll threshold hook (NavBar transparency)
│   ├── useDebounce.js          # Search input debounce
│   └── useInfiniteScroll.js    # IntersectionObserver scroll hook
│
└── data.js                     # 90-genre GLOBAL_GENRES list + matchGenres + isValidGenre
```

---

## Core Features Deep Dive

### Video Player

Built on `react-player` with a fully custom control overlay. Controls auto-hide after 3 seconds of playback inactivity. The **quality selector** in the settings gear derives available options from the video's uploaded quality field (e.g. a `1080p` upload shows `1080p → 720p → 480p → 360p`). Subtitle tracks are injected via `config.file.tracks`; toggling uses the `textTracks` DOM API directly because ReactPlayer does not re-render tracks reactively.

### Dynamic Genre System

Genres are validated at upload against a 90-entry `GLOBAL_GENRES` list. The CategoryBar queries Firestore on mount for categories that have at least one video — the navigation bar grows organically as content is added.

```
Upload → genre validated client-side → stored in Firestore
→ CategoryBar queries unique categories on mount → pill appears automatically
```

### User Dashboard

All queries are scoped to the authenticated user's UID via Zustand's persisted auth store. Recharts renders dark-themed bar and area charts. The font family picker calls `preloadAllFonts()` on mount to inject all 8 Google Font stylesheets simultaneously so previews render without flash.

### Admin Panel

Protected by a Zustand hydration-aware `AdminGuard` that waits for `persist` to restore the auth state before evaluating the role — preventing false redirects on page reload. The featured video toggle writes `featured: true` to Firestore; `getFeaturedVideo()` checks this flag first before falling back to the latest upload for the hero section.

### Font System

```
Settings UI → select font → applyFont(name) called immediately
           → <link> injected to Google Fonts CDN
           → document.body.style.fontFamily updated
           → saved to Firestore settings/app
           → App.jsx reads settings on every load → applyFont() called on startup
```

---

## Deployment

```bash
npm run build
firebase deploy
```

`firebase.json` includes a catch-all rewrite so React Router handles all deep links in production:

```json
{
  "hosting": {
    "public": "build",
    "rewrites": [{ "source": "**", "destination": "/index.html" }]
  }
}
```

---

## Roadmap

- [ ] Firebase Cloud Functions — atomic view/like counters, real storage stats, admin Auth user deletion
- [ ] Rate limiting — per-user upload quotas enforced server-side
- [ ] Comments — threaded comments on video detail pages
- [ ] Push notifications — Firebase Cloud Messaging for new content
- [ ] Infinite scroll on category pages — Firestore cursor-based pagination
- [ ] Video transcoding — multiple quality renditions via Cloud Functions + FFmpeg

---

## Contributing

Contributions are welcome. Open an issue first to discuss what you would like to change.

```bash
git checkout -b feature/your-feature-name
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# open a Pull Request
```

---

## License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

Built by **Digvijay Shingare** — Full Stack Developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Digvijay_Shingare-0077b5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/digvijay-shingare)
[![GitHub](https://img.shields.io/badge/GitHub-digvijay--shingare-181717?style=flat-square&logo=github)](https://github.com/digvijay-shingare)

</div>
