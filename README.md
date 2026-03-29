# 📣 Ad Campaign Redirect Website

> A Next.js-based ad campaign flow website — routes users through a series of offer pages before redirecting to the final destination.

---

## 🏗️ How It Works

Users enter the site and are guided through a sequence of offer pages. Each page either presents an ad/offer or redirects the user forward in the funnel until they reach the final destination.

```
User Lands
    │
    ▼
page.tsx  (Entry / Landing Page)
    │
    ▼
offer1  →  offer2  →  offer3  →  offer4  →  offer5
                                                │
                                                ▼
                                          redirect/page.tsx
                                                │
                                                ▼
                                      Final Destination URL
```

> See **`CAMPAIGN_FLOW.md`** for the detailed campaign routing logic.

---

## 📁 Project Structure

```
ad-redirect/
├── public/                     # Static SVG assets
├── src/
│   └── app/
│       ├── page.tsx            # Entry landing page
│       ├── layout.tsx          # Root layout
│       ├── globals.css         # Global styles
│       ├── blankPage/
│       │   └── page.tsx        # Blank interstitial page
│       ├── offer1/
│       │   └── page.tsx        # Offer page 1
│       ├── offer2/
│       │   └── page.tsx        # Offer page 2
│       ├── offer3/
│       │   └── page.tsx        # Offer page 3
│       ├── offer4/
│       │   └── page.tsx        # Offer page 4
│       ├── offer5/
│       │   └── page.tsx        # Offer page 5
│       └── redirect/
│           └── page.tsx        # Final redirect handler
├── CAMPAIGN_FLOW.md            # Campaign routing documentation
├── next.config.ts              # Next.js configuration
├── tsconfig.json               # TypeScript config
└── package.json
```

---

## 🗺️ Page Routes

| Route | File | Description |
|-------|------|-------------|
| `/` | `app/page.tsx` | Entry point — first page users see |
| `/blankPage` | `blankPage/page.tsx` | Blank interstitial / buffer page |
| `/offer1` | `offer1/page.tsx` | Ad offer page 1 |
| `/offer2` | `offer2/page.tsx` | Ad offer page 2 |
| `/offer3` | `offer3/page.tsx` | Ad offer page 3 |
| `/offer4` | `offer4/page.tsx` | Ad offer page 4 |
| `/offer5` | `offer5/page.tsx` | Ad offer page 5 |
| `/redirect` | `redirect/page.tsx` | Final redirect to destination URL |

---

## ⚙️ Prerequisites

| Tool | Version |
|------|---------|
| Node.js | 18+ |
| npm / bun | Latest |

---

## 🚀 Getting Started

### Step 1 — Clone the Repository

```bash
git clone <repository-url>
cd ad-redirect
```

### Step 2 — Install Dependencies

**Using npm:**
```bash
npm install
```

**Using bun:**
```bash
bun install
```

### Step 3 — Start the Development Server

**Using npm:**
```bash
npm run dev
```

**Using bun:**
```bash
bun dev
```

> ✅ The app should now be running at **`http://localhost:3000`**

---

## 📦 Build for Production

```bash
npm run build
npm start
```

---

## 🌐 Deployment

This project is optimized for **Vercel** deployment.

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel
```

Or connect your GitHub repository directly on [vercel.com](https://vercel.com) for automatic deployments on every push.

---

## 🛠️ Built With

| Technology | Purpose |
|------------|---------|
| Next.js 14+ | React framework with App Router |
| TypeScript | Type-safe development |
| Tailwind CSS | Utility-first styling |
| Bun | Fast JavaScript runtime & package manager |
| Vercel | Hosting & deployment |

---

## 📋 Campaign Flow

The full campaign routing logic is documented in **`CAMPAIGN_FLOW.md`**. Refer to it when:
- Adding or reordering offer pages
- Changing redirect destination URLs
- Updating campaign parameters or tracking tokens

---

## 🛠️ Troubleshooting

**Port 3000 already in use?**
```bash
npm run dev -- -p 3001
```

**Bun lockfile conflicts with npm?**
- Use one package manager consistently — either `bun install` or `npm install`, not both

**Redirect not working in production?**
- Check `next.config.ts` for any redirect or rewrite rules
- Verify the destination URL is correctly set in `redirect/page.tsx`
- 
