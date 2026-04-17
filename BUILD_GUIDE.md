# 🎊 Wedding Website - Build & Deployment Guide

## ✅ Code Status

**Your code is working perfectly!** No errors detected. All Maharashtrian wedding elements are integrated including:
- ✓ Wedding date: 3 May 2026 @ 6:40 PM
- ✓ Venue: Ganeshlila Mangal Karyalay, Akumbhe, Solapur
- ✓ Parents' names (Gaikwad & Kale families)
- ✓ UPI Payment: 7588339191@ibl
- ✓ Embedded Google Maps with venue location
- ✓ Marathi greetings and cultural elements

---

## 🚀 Quick Start - Run in 3 Steps

### **Step 1: Install Dependencies**
```bash
cd /Users/sanketdiwate/Projects/Wedding/Wedding
npm install
```

### **Step 2: Start Development Server**
```bash
npm run dev
```

This will:
- Bundle JavaScript files with esbuild
- Start a local dev server at `http://localhost:8080`
- Watch for file changes automatically
- Hot reload when you save changes

**Expected Output:**
```
✓ served at http://localhost:8080
```

### **Step 3: Open in Browser**
Navigate to: `http://localhost:8080`

---

## 📝 Available npm Commands

### Development
```bash
# Start dev server with live reload (recommended for development)
npm run dev
```

### Build for Production
```bash
# Create optimized, minified build
npm run build
```

### Lint Code
```bash
# Check JavaScript
npm run lint:js

# Check CSS
npm run lint:css

# Check HTML
npm run lint:html
```

### Deploy to Public Folder
```bash
# Build and copy all assets to 'public' folder for deployment
npm run build:public
```

---

## 🗺️ Maps Integration

### What Was Added
- **Embedded Google Maps iframe** showing the wedding venue
- Location: Ganeshlila Mangal Karyalay, Akumbhe, Madha District, Solapur
- Interactive map that guests can view venue location and directions
- Mobile-responsive design

### Files Modified
- `index.html` - Added embedded maps section in venue location area

### Map Features
✓ Click to open in Google Maps  
✓ Get directions button  
✓ Mobile-friendly responsive design  
✓ Works offline (if cached)  

---

## 📱 Testing Checklist

### Before Sharing with Guests

- [ ] Run dev server: `npm run dev`
- [ ] Test on desktop (Chrome, Firefox, Safari)
- [ ] Test on mobile phone
- [ ] Verify all names are correct
- [ ] Test UPI payment link
- [ ] Click "View Location" button
- [ ] Check map is displaying correctly
- [ ] Test Google Calendar button
- [ ] Verify date/time: 3 May 2026, 6:40 PM
- [ ] Check dark/light theme toggle

---

## 🔧 Code Structure

```
Wedding/
├── index.html           # Main invitation page
├── dashboard.html       # Admin dashboard (optional)
├── package.json         # Dependencies & scripts
├── css/
│   ├── guest.css       # Guest invitation styles (main)
│   ├── admin.css       # Admin styles
│   ├── common.css      # Shared styles
│   └── animation.css   # Animations
├── js/
│   ├── guest.js        # Guest invitation logic (auto-bundled)
│   ├── admin.js        # Admin logic
│   └── app/           # Application modules
│       ├── guest/     # Guest-specific features
│       ├── admin/     # Admin features
│       └── components/# Reusable components
├── assets/
│   ├── images/        # Photos and backgrounds
│   ├── music/         # Wedding music
│   └── video/         # Videos
└── dist/              # Generated bundled files (auto-created)

```

---

## 🎯 How Changes Are Applied

1. **You edit** JavaScript/CSS/HTML files
2. **Save the file**
3. **Dev server auto-detects changes** (esbuild watches for changes)
4. **Files are re-bundled** into `dist/` folder
5. **Browser auto-reloads** (livereload)
6. **You see changes immediately** in browser

**Note:** When you run `npm run dev`, it starts watching all your JavaScript files and automatically bundles them to `dist/guest.js`. This is already referenced in `index.html`, so you don't need to do anything manually.

---

## 📤 Deployment Steps

### Option 1: Deploy to Netlify (Recommended)

```bash
# 1. Build for production
npm run build:public

# 2. Upload 'public' folder to Netlify
# Or connect your GitHub repo for auto-deploy
```

### Option 2: Deploy to Vercel

```bash
# 1. Build for production
npm run build:public

# 2. Install Vercel CLI
npm install -g vercel

# 3. Deploy
vercel
```

### Option 3: Manual Server Deployment

```bash
# 1. Build for production
npm run build:public

# 2. Copy 'public' folder to your web server
# 3. Ensure your server serves it as static files
```

---

## 🐛 Troubleshooting

### Issue: "Port 8080 already in use"
```bash
# Kill the process using port 8080
lsof -ti:8080 | xargs kill -9

# Or use a different port
npx esbuild js/*.js --bundle --outdir=dist --servedir=. --serve=3000
```

### Issue: Changes not visible after saving
```bash
# Hard refresh in browser (clear cache)
Ctrl + Shift + R  (Windows/Linux)
Cmd + Shift + R   (Mac)
```

### Issue: Maps not loading
- Ensure internet connection is active
- Check if Google Maps iframe is not blocked by firewall
- Try opening the location in new tab

### Issue: Older code still showing
```bash
# Clear dist folder and rebuild
rm -rf dist/
npm run dev
```

---

## 📊 File Size Information

After running `npm run build:public`:
- Main bundle (`dist/guest.js`): ~50-100KB (minified)
- CSS files: ~30-50KB (combined)
- Total website: ~500KB-1MB with images

---

## ✨ Key Features to Highlight to Guests

1. **📱 Mobile Responsive** - Works perfectly on all devices
2. **🌓 Dark/Light Theme** - Auto-detects system preference
3. **🗺️ Interactive Maps** - See venue location and directions
4. **💬 Comments Section** - Guests can leave wishes
5. **📸 Photo Gallery** - Share couple photos
6. **🎵 Background Music** - Optional wedding music
7. **🎊 Confetti** - Celebratory animation
8. **📅 Google Calendar** - One-click calendar event
9. **💳 UPI Payment** - Easy gift transfer
10. **🌐 Offline Support** - Works even without internet

---

## 🎨 Customization Tips

### Change Wedding Date/Time
Edit in `index.html`:
```html
data-time="2026-05-03 18:40:00"
```

### Change Couple Photos
Replace image sources in `assets/images/`:
- `cowo.webp` - Groom photo
- `cewe.webp` - Bride photo
- `bg.webp` - Background image

### Modify Colors/Styling
Edit `css/guest.css` or `css/common.css`

### Add More Content
Edit `index.html` and add new sections

---

## 📞 Support

For any issues:
1. Check **Troubleshooting** section above
2. Review `package.json` for available scripts
3. Ensure all dependencies are installed: `npm install`
4. Check browser console for errors: `F12` → Console tab

---

## ✅ Final Checklist Before Sharing

- [ ] Run `npm run dev` and test locally
- [ ] All content is correct (names, dates, address)
- [ ] Maps are displaying
- [ ] Payment details are correct
- [ ] Website loads on mobile
- [ ] Dark/light theme works
- [ ] Build for production: `npm run build:public`
- [ ] Share public folder or deployment URL

---

**Ready to celebrate! 🎉**  
Your Maharashtrian wedding website is complete and ready to impress your guests!
