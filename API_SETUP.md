# 🔧 Self-Hosted API Setup Guide

This wedding invitation frontend is wired to use **your own backend API**.
You need to deploy `undangan-api` and then update two lines in this repo.

---

## Step 1 — Deploy your own backend

1. Fork the backend repo: https://github.com/dewanakl/undangan-api
2. Clone and install:
   ```bash
   git clone https://github.com/<your-username>/undangan-api.git
   cd undangan-api
   composer install
   cp .env.example .env
   ```
3. Edit `.env`:
   ```env
   BASE_URL=https://api.yourdomain.com
   DB_HOST=localhost
   DB_NAME=wedding_api
   DB_USER=your_db_user
   DB_PASS=your_db_password
   ```
4. Run migrations:
   ```bash
   php kamu migrate
   ```
5. Deploy to your PHP host / VPS. Point your subdomain (e.g. `api.yourdomain.com`) to the `public/` folder.

---

## Step 2 — Create your admin account & get Access Key

1. Open `https://api.yourdomain.com` in browser → register admin (email + password)
2. Log in → go to Settings tab → copy your **Access Key**

---

## Step 3 — Update this frontend repo

In `index.html`, find the `<body>` tag and replace:

```html
<!-- CONFIGURE: Replace YOUR_API_URL with your deployed backend URL (with trailing slash) -->
<!-- CONFIGURE: Replace YOUR_ACCESS_KEY with the key from your dashboard Settings tab -->
<body
  data-key="YOUR_ACCESS_KEY"
  data-url="YOUR_API_URL"
  ...
>
```

In `dashboard.html`, find the `<body>` tag and replace:

```html
<!-- CONFIGURE: Replace YOUR_API_URL with your deployed backend URL (with trailing slash) -->
<body data-url="YOUR_API_URL">
```

---

## Step 4 — Build & Deploy frontend

```bash
npm install
npm run build:public
```

Deploy the generated `public/` folder to Netlify / GitHub Pages / Vercel.

On Netlify:
- Build command: `npm run build:public`
- Publish directory: `public`

---

## Access Key Notes

- The `data-key` in `index.html` is your **invitation access key** (not your admin password).
- You can regenerate it anytime from the dashboard → Settings → Access Key → Regenerate.
- After regenerating, update `data-key` in `index.html` and redeploy.

---

## Local Dev

```bash
npm run dev
# Opens http://localhost:8080
# Test guest page: http://localhost:8080/?to=YourName
# Test dashboard: http://localhost:8080/dashboard.html
```
