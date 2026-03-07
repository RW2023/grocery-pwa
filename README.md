# Grocery List PWA

A voice-powered family grocery list app. Add items by speaking, track inventory, and manage shared shopping lists across the household.

**Live:** [grocery-pwa-iota.vercel.app](https://grocery-pwa-iota.vercel.app)

## Features

- **Voice Input** -- Add groceries by speaking naturally ("we need milk"). Uses the Web Speech API with speaker attribution.
- **Shared Family List** -- Multiple family members contribute to one list. Each item tracks who requested it.
- **Smart Categories** -- Items auto-sort into produce, dairy, meat, bakery, frozen, pantry, snacks, beverages, and household.
- **Inventory Tracking** -- Track stock levels (Out, Low, Stocked) with purchase history per item.
- **Dislike System** -- Family members can flag items they don't want. Warnings appear when someone tries to add a disliked item.
- **Admin Mode** -- PIN-protected admin panel for editing items, clearing history, and managing the list.
- **Dark/Light Mode** -- Theme toggle that syncs with system preferences.
- **Installable PWA** -- Add to home screen for a native app experience with offline support.
- **Stats Dashboard** -- Live counts of tracked items, purchases, and dislikes.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML/CSS/JavaScript (single-file PWA) |
| Voice | Web Speech API |
| Backend | n8n automation workflows |
| Database | PostgreSQL (Neon) |
| Auth | Family password + API key |
| Deployment | Vercel |
| PWA | Service worker + web manifest |

## Architecture

This is a zero-framework PWA. The entire app is a single `index.html` file with embedded CSS and JavaScript. The backend runs on n8n workflows that handle:

- Authentication and session management
- Item CRUD operations
- Inventory state tracking
- Purchase history logging
- Family member management

All data persists in a PostgreSQL database via n8n API endpoints.

## Getting Started

```bash
# Clone
git clone https://github.com/RW2023/grocery-pwa.git
cd grocery-pwa

# Serve locally (any static server works)
npx serve .
```

The app requires a running n8n instance with the grocery workflows configured. See the backend setup in the companion workflow files.
