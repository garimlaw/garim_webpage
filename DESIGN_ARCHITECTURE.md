# Garim's Personal Website — Rockman Theme

## 1) Project Goal

Build a personal website that is simple, clear, and beginner-friendly, with a classic Rockman (Mega Man) game vibe.

Primary content:
- Profile / About
- Skills
- Projects
- Contact info

Design principle:
- Retro game style on top of a modern, maintainable codebase.

---

## 2) Final Stack Decision (Option A)

| Layer | Tech | Why this choice |
|---|---|---|
| Framework | **Next.js (React, App Router)** | Easy routing, strong docs, real-world standard |
| Styling | **Tailwind CSS** | Fast styling workflow for beginners |
| Animation | **Framer Motion** | Simple API for smooth UI transitions |
| Hosting | **Vercel** | Easiest deployment for Next.js |

**Decision:** Use Option A for MVP.

---

## 3) User Journey

```text
Landing (Stage Select)
	├─ About
	├─ Skills
	├─ Projects
	└─ Contact
```

How it should feel:
1. User lands on stage-select screen.
2. User chooses a menu panel.
3. User reads focused content quickly.
4. User can always navigate back to stage select.

---

## 4) Information Architecture

### Routes
- `/` → Stage Select (main menu)
- `/about` → Profile and short intro
- `/skills` → Skill list grouped by category
- `/projects` → Project cards with links
- `/contact` → Contact form + social links

### Content Model (simple data files)
- `skills.ts`
	- `name`, `category`, `level`, `icon`
- `projects.ts`
	- `title`, `description`, `tech`, `demoUrl`, `repoUrl`

---

## 5) UI & Theme Guidelines (Rockman)

### Visual style
- Dark base background
- Neon blue/yellow/green accents
- Pixel-inspired font for titles
- Clean body font for readability

### Color palette
| Token | Hex | Usage |
|---|---|---|
| `bg.base` | `#0D0D1A` | Main background |
| `bg.panel` | `#1A1A2E` | Cards/panels |
| `brand.primary` | `#00BFFF` | Primary highlight |
| `brand.energy` | `#FFD700` | Active state / buttons |
| `brand.success` | `#39FF14` | Bars / positive state |
| `brand.danger` | `#FF3131` | Error / warning |
| `text.primary` | `#E0E0FF` | Main text |

Font plan:
- Heading: `Press Start 2P`
- Body: system sans-serif (for easier reading)

---

## 6) Page-by-Page Blueprint

### `/` Landing — Stage Select
- 4 main panels: About, Skills, Projects, Contact
- Panel hover: glow + slight scale
- Keyboard accessible (Tab + Enter)

### `/about`
- Profile image/avatar
- 3–5 sentence intro
- Fun stat/health bar component

### `/skills`
- Skills grouped: Frontend, Backend, Tools
- Each skill shown as "weapon chip" or energy bar style

### `/projects`
- Project cards with title, short description, stack tags
- Buttons: `Live Demo` and `GitHub`

### `/contact`
- Simple form: name, email, message
- Social links (GitHub, LinkedIn, etc.)

---

## 7) Animation Rules (Framer Motion)

Keep animation lightweight and purposeful.

| Area | Motion |
|---|---|
| Page enter | Fade + slight slide-up |
| Stage panels | Hover glow + scale `1.03` |
| Section content | Stagger reveal for cards/items |
| Buttons | Small tap/press feedback |

Rule:
- If animation distracts from reading, reduce it.

---

## 8) Folder Architecture (Planned)

```text
garim_webpage/
├─ public/
│  ├─ images/
│  └─ icons/
├─ src/
│  ├─ app/
│  │  ├─ layout.tsx
│  │  ├─ page.tsx
│  │  ├─ about/page.tsx
│  │  ├─ skills/page.tsx
│  │  ├─ projects/page.tsx
│  │  └─ contact/page.tsx
│  ├─ components/
│  │  ├─ StagePanel.tsx
│  │  ├─ StageSelectGrid.tsx
│  │  ├─ Navbar.tsx
│  │  ├─ WeaponChip.tsx
│  │  ├─ ProjectCard.tsx
│  │  ├─ HealthBar.tsx
│  │  └─ ContactForm.tsx
│  ├─ data/
│  │  ├─ skills.ts
│  │  └─ projects.ts
│  └─ styles/
│     └─ globals.css
├─ tailwind.config.ts
├─ next.config.ts
└─ package.json
```

---

## 9) Beginner Build Pipeline (Execution Order)

### Phase 1 — Setup
1. Create Next.js app.
2. Verify local run (`npm run dev`).
3. Install/configure Tailwind and Framer Motion.

### Phase 2 — Foundation
1. Add global theme colors and fonts.
2. Build layout + navigation shell.
3. Build stage select page first.

### Phase 3 — Core Pages
1. Build About.
2. Build Skills using static data file.
3. Build Projects using static data file.
4. Build Contact form UI.

### Phase 4 — Motion & Polish
1. Add minimal Framer Motion transitions.
2. Improve responsive layout (mobile/tablet/desktop).
3. Accessibility pass (focus states, contrast, alt text).

### Phase 5 — Deploy
1. Push to GitHub.
2. Connect repository to Vercel.
3. Deploy production URL.

---

## 10) MVP Scope (What to Build First)

Must-have:
- 5 routes (`/`, `/about`, `/skills`, `/projects`, `/contact`)
- Working navigation
- Rockman visual identity
- Responsive layout
- Deployed on Vercel

Not in MVP (later):
- Blog system
- Audio/music controls
- Konami code easter egg
- CMS integration

---

## 11) Definition of Done

Project is "done" when:
- All 5 pages are complete and linked.
- Design theme is consistent across pages.
- Site works on mobile and desktop.
- No blocking console/runtime errors.
- Live URL is deployed and shareable.

---

## 12) Future Enhancements (After MVP)

- Add blog with MDX.
- Add project filters and search.
- Add fun retro loading animation.
- Add dark/light "Power Mode" switch.

---

## 13) Reference Notes

This document is the single planning reference for implementation.

When starting build work, follow this order:
1. Section 9 (Pipeline)
2. Section 10 (MVP scope)
3. Section 11 (Definition of done)
