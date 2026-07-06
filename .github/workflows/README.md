# ScholarMatch

A comprehensive smart scholarship & university matching web application built with **Next.js 16**, **Tailwind CSS v4**, and **TypeScript**.

> Find your perfect scholarship in one click. Built for students in Cameroon and ambitious students worldwide.

---

## ✨ Features

### 🔐 Authentication
- **Google OAuth** sign-in (simulated; drop-in ready for production)
- **Email/Password** sign-up & sign-in
- **Admin-only access** restricted to a single email: `diakeyves3@gmail.com`

### 🎓 Student Portal
- **Discovery Engine** — modern dashboard with filters (Country, Field, Budget, Degree Level) and sortable match-score cards
- **Expandable Cards** — eligibility, required docs, financial-gap calculator, and external one-click links
- **Application Tracker** — Kanban board (Draft → Submitted → Under Review → Accepted / Rejected) + list view with progress bars, deadline urgency badges, and document checklists
- **Document Vault** — drag-and-drop upload, type categorization (transcript, CV, passport, etc.), preview & reuse across applications
- **Profile Editor** — adjustable GPA, budget, field, degree, country, language tests
- **One-Click Apply** — auto-attaches uploaded documents, creates an application record, and opens the official portal in a new tab

### 🛡️ Admin Panel
- **Sidebar navigation** (Overview, Scholarships, Universities, Students)
- **Analytics dashboard** — total funding value, country coverage, top fields of study, application funnel
- **Full CRUD** — add, edit, delete scholarships & universities via modal forms
- **One-click external links** — every row has direct `Visit` and `Apply` buttons
- **Student monitoring** — view profiles, GPA, app counts, recent activity

### 🎨 Design
- Clean, responsive UI (mobile sidebar, sticky headers)
- Skeleton loaders on all data fetches
- 18 scholarships, 12 universities, 7 mock students, 5 mock applications preloaded
- **Cameroon** is the default country throughout

---

## 🚀 Getting Started

```bash
cd scholarmatch
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Try the demo

| Role | Email | Password |
|------|-------|----------|
| **Admin** | `diakeyves3@gmail.com` | any 6+ chars |
| **Student** | any email | any 6+ chars |
| **Google** | click "Continue with Google" | — |

After signing in:
- Admin → redirected to `/admin`
- Student → redirected to `/dashboard`

---

## 🧱 Project Structure

```
scholarmatch/
├── app/
│   ├── layout.tsx                 # Root layout + AuthProvider
│   ├── page.tsx                   # Landing page
│   ├── login/, signup/            # Auth pages
│   ├── dashboard/
│   │   ├── page.tsx               # Discovery engine
│   │   ├── applications/          # Kanban tracker
│   │   ├── documents/             # Document vault
│   │   └── profile/               # Profile editor
│   └── admin/
│       ├── page.tsx               # Analytics overview
│       ├── scholarships/          # Manage scholarships
│       ├── universities/          # Manage universities
│       └── students/              # Monitor students
├── components/
│   ├── ui/                        # Reusable: Logo, Button, Modal, Badge, Skeleton
│   ├── AdminSidebar, AdminTopBar
│   ├── StudentSidebar, StudentTopBar
│   └── profile-context.tsx
├── lib/
│   ├── types.ts                   # All TypeScript types
│   ├── mockData.ts                # 18 scholarships + 12 unis + students + apps
│   ├── auth-context.tsx           # Auth provider + Google/email login
│   ├── storage.ts                 # LocalStorage persistence
│   └── utils.ts                   # Match scoring, gap calculator, deadlines
└── ...
```

---

## 🔧 How the One-Click Apply Works

When a student clicks **Apply** (or "Apply in one click"):

1. **Review screen** — shows the program and which documents will be attached
2. **Auto-fill** — validates required documents from the user's vault (warns if missing)
3. **Launch** — creates an `Application` record (status: Submitted), opens the official portal in a new tab
4. **Tracker updated** — the application appears in the student's Kanban board under "Submitted"

This works as a true automation pipeline using the data already provided by the user in their vault.

---

## 📦 Tech Stack

- **Next.js 16** (App Router, Turbopack)
- **React 19**
- **Tailwind CSS v4**
- **TypeScript 5**
- **LocalStorage** for client-side persistence (drop-in ready for a backend like Supabase or Prisma)

---

Built with 💜 for students in Cameroon and beyond.
