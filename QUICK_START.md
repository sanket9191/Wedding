# ⚡ QUICK RENDER & BUILD COMMANDS

## 🎯 To See Your Changes (3 Steps)

### Step 1: Open Terminal
```bash
cd /Users/sanketdiwate/Projects/Wedding/Wedding
```

### Step 2: Start Development Server
```bash
npm run dev
```

### Step 3: View in Browser
```
http://localhost:8080
```

**That's it!** The website will auto-refresh when you save files.

---

## 🔄 Build Process Explained

### What Happens When You Run `npm run dev`:

```
┌─────────────────────────────────────────────────────┐
│  npm run dev                                         │
│  (Watches JavaScript files)                        │
└──────────────────┬──────────────────────────────────┘
                   │
          ┌────────▼────────┐
          │  esbuild        │
          │  (Bundler)      │
          └────────┬────────┘
                   │
          ┌────────▼────────────┐
          │ dist/guest.js       │
          │ (Generated Bundle)  │
          └────────┬────────────┘
                   │
          ┌────────▼────────────┐
          │ Browser (Port 8080) │
          │ Serves HTML + JS    │
          └────────────────────┘
                   │
          ┌────────▼──────────────┐
          │ Your Website Live!    │
          │ Hot Reload on Changes │
          └──────────────────────┘
```

---

## 📝 What Changed Today

### ✅ Maps Section Added
- **File:** `index.html`
- **Location:** In venue section (line ~391)
- **What:** Embedded Google Maps iframe showing wedding venue
- **Features:**
  - Interactive map showing Akumbhe, Solapur
  - Guests can see directions
  - Mobile responsive
  - Height: 300px on desktop

### ✅ Build Guide Created
- **File:** `BUILD_GUIDE.md`
- **Location:** Wedding/ folder root
- **Contains:** Complete deployment & customization guide

---

## 🚀 Deploy to Live (After Testing)

### Build Production Version
```bash
npm run build:public
```

This creates a `public/` folder with everything ready to deploy.

### Upload to Hosting
1. **Netlify (Recommended):**
   - Drag & drop `public/` folder to [netlify.app](https://netlify.app)
   
2. **GitHub Pages:**
   - Push `public/` folder to GitHub
   
3. **Any Web Server:**
   - Upload `public/` contents to your server

---

## ✅ Code Status Summary

| Item | Status | Details |
|------|--------|---------|
| **Errors** | ✅ None | Code compiles perfectly |
| **Wedding Data** | ✅ Complete | All dates, names, venue set |
| **Maps** | ✅ Added | Google Maps embedded |
| **Marathi Content** | ✅ Integrated | Verses, greetings, cultural elements |
| **Responsive Design** | ✅ Ready | Works on all devices |
| **Build Process** | ✅ Automated | esbuild handles bundling |

---

## 🐛 If Something Breaks

### Quick Fix Checklist
```bash
# 1. Stop server (Ctrl + C in terminal)

# 2. Clear cache
rm -rf dist/

# 3. Reinstall dependencies
npm install

# 4. Start fresh
npm run dev
```

### Clear Browser Cache
- **Windows/Linux:** `Ctrl + Shift + Delete`
- **Mac:** `Cmd + Shift + Delete` or Settings → Privacy

---

## 📱 Test on Multiple Devices

```bash
# While dev server is running on localhost:8080
# Your local IP address (replace XXX):
http://192.168.X.XXX:8080

# Find your IP:
# Mac/Linux:
ifconfig | grep "inet "

# Windows:
ipconfig
```

---

## 🎨 Live Edit During Development

1. Save changes to any file
2. Dev server detects changes (usually within 1-2 seconds)
3. Browser auto-refreshes
4. See your changes immediately

**No manual build needed during development!**

---

## 📊 File Sizes (After Build)

- JavaScript Bundle (`dist/guest.js`): ~60KB
- CSS Files: ~40KB
- HTML: ~80KB
- Images: Variable (compress before uploading)
- **Total:** ~1MB with images

---

## 🎉 You're All Set!

```bash
# One command to rule them all:
npm run dev

# Then visit:
http://localhost:8080
```

**Enjoy building your wedding website! 🎊**
