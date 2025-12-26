# Corporate Actions Tracker - Mobile PWA

A Progressive Web App (PWA) for tracking corporate actions (dividends, stock splits) and calculating investment returns.

## Features

- 📊 Track dividend history and upcoming payments
- ✂️ View stock split history
- 💰 Calculate investment returns including dividends
- 📈 Dividend yield and growth rate analysis (1Y, 3Y, 5Y CAGR)
- 📱 Install on your phone as a native-like app
- 🔄 Works offline (cached data)
- 💾 Saves your API key and recent searches locally

## Installation

### Option 1: Host on a Free Service (Recommended)

#### Using Netlify (Easiest)
1. Go to [netlify.com](https://netlify.com) and sign up
2. Click "Add new site" → "Deploy manually"
3. Drag and drop the entire `corporate-actions-pwa` folder
4. Your site will be live at `https://[random-name].netlify.app`
5. Open that URL on your phone and install (see below)

#### Using GitHub Pages
1. Create a new GitHub repository
2. Upload all files from this folder
3. Go to Settings → Pages → Select "main" branch
4. Your site will be at `https://[username].github.io/[repo-name]`

#### Using Vercel
1. Go to [vercel.com](https://vercel.com) and sign up
2. Click "Add New..." → "Project"
3. Upload the folder or connect to GitHub
4. Your site will be live instantly

### Option 2: Run Locally

```bash
# Using Python (built-in)
cd corporate-actions-pwa
python3 -m http.server 8080

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8080
```

Then open `http://localhost:8080` in your browser.

**Note:** For the install prompt to work, you need HTTPS. Local development works but won't show the install banner.

## Installing on Your Phone

### Android
1. Open the hosted URL in Chrome
2. Tap the menu (⋮) → "Add to Home screen"
3. Or wait for the install banner to appear

### iPhone/iPad
1. Open the hosted URL in Safari
2. Tap the Share button (□↑)
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add"

## Usage

1. Get a free API key from [polygon.io](https://polygon.io)
2. Enter your API key (saved automatically)
3. Enter a stock ticker (e.g., AAPL, MSFT, JNJ)
4. View dividend history, splits, and calculate returns

## Files Structure

```
corporate-actions-pwa/
├── index.html      # Main app (HTML + React)
├── manifest.json   # PWA manifest for installation
├── sw.js           # Service worker for offline support
├── icons/          # App icons
│   ├── icon-192.svg
│   └── icon-512.svg
└── README.md       # This file
```

## API Limits

The free Polygon.io tier includes:
- 5 API calls per minute
- 2 years of historical data
- End of day data

For more data, consider upgrading at [polygon.io/pricing](https://polygon.io/pricing)

## Troubleshooting

**Install prompt not showing?**
- Make sure you're on HTTPS (required for PWAs)
- Try clearing browser cache
- On iOS, you must use Safari

**Data not loading?**
- Check your API key is correct
- Verify the ticker symbol exists
- Check your internet connection

**Offline mode not working?**
- Visit the site while online first to cache assets
- The service worker needs to install on first visit

## Privacy

- Your API key is stored locally in your browser only
- No data is sent to any third-party servers
- All API calls go directly to Polygon.io
