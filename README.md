# GeminiClean — Deployment & Monetization Guide

Free browser-based tool to remove the Gemini AI sparkle logo from videos.

---

## 🚀 Deploy in 10 Minutes (Netlify — Recommended)

1. Go to https://netlify.com and sign up (free)
2. Drag the entire `geminiclean/` folder onto the Netlify dashboard
3. Netlify auto-deploys. You'll get a URL like `geminiclean.netlify.app`
4. Buy a domain like `geminiclean.com` (~$12/yr on Namecheap) and connect it in Netlify settings

> The `_headers` file is already included — it enables SharedArrayBuffer for faster video processing.

---

## 💰 Google AdSense Setup

1. Apply at https://adsense.google.com (needs live site + some content)
2. Once approved, replace the 3 ad placeholder `<div>` blocks in `index.html` with your AdSense code:
   - **Leaderboard 728×90** — top of page (high visibility = high RPM)
   - **Rectangle 300×250** — sidebar top
   - **Rectangle 300×250** — sidebar bottom

Search for `<!-- PASTE YOUR ADSENSE` in the HTML to find the exact locations.

### Estimated Revenue (rough estimates)
- Traffic: 1,000 visitors/day
- RPM (revenue per 1,000 views): $2–$6 for a tool like this
- Monthly: ~$60–$180 at 1k/day traffic

Scale with SEO to 10k/day → $600–$1,800/month.

---

## 🔍 Google Search Console Setup

1. Go to https://search.google.com/search-console
2. Add your domain as a property
3. Verify ownership (Netlify makes this easy via DNS TXT record)
4. Submit your sitemap: `https://yoursite.com/sitemap.xml`

### Add a sitemap (optional but good for SEO)
Create `sitemap.xml` in the root:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://geminiclean.com/</loc>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

---

## 🎯 SEO Strategy — Keywords to Target

High-intent, low-competition keywords right now:
- `remove gemini logo from video`
- `gemini video watermark remover`
- `veo logo remover`
- `gemini sparkle logo remove`
- `how to remove gemini logo`

Add these naturally in the FAQ section (already included in index.html).

---

## ⚡ Alternative: Vercel Deployment

1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` inside the `geminiclean/` folder
3. Follow prompts — done in 2 minutes

The `vercel.json` file is already configured.

---

## 📁 File Structure

```
geminiclean/
├── index.html      ← The entire website (single file)
├── _headers        ← Netlify: enables SharedArrayBuffer
├── vercel.json     ← Vercel: same headers config
└── README.md       ← This file
```

---

## 🔧 Customization

- **Change site name**: Search/replace `GeminiClean` in index.html
- **Change accent color**: Edit `--accent: #00d9b8` in the CSS variables
- **Add Google Analytics**: Paste GA4 script tag in the `<head>`
- **Logo position tweak**: Edit `delogoPx()` function in the JS if needed for different video sizes
