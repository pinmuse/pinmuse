# PinMuse — Static Website

Official website for **PinMuse**, a mobile fashion technology app that helps users recreate Pinterest-inspired outfits using AI-powered wardrobe matching and weather-aware styling.

**Live URL:** https://pinmuse.com

---

## Project Overview

This is a fully static website with no framework, no build tools, and no backend required. It is designed to satisfy Pinterest Developer App review requirements, including a publicly accessible site with a real Privacy Policy hosted on a proper custom domain.

---

## Folder Structure

```
PinMuse-Homepage/
├── index.html              # Landing page
├── privacy-policy.html     # Privacy Policy (required for Pinterest API review)
├── imprint.html            # German Impressum / legal notice
├── styles.css              # All styles (single shared stylesheet)
├── assets/
│   └── logo-placeholder.svg   # App logo / icon placeholder
└── README.md
```

---

## Before Publishing

1. **Replace the logo:** Swap `assets/logo-placeholder.svg` with your production app icon (`assets/logo-placeholder.png` or `.svg`). Update `<img src="...">` references in all HTML files if you rename the file.
2. **Complete the Imprint:** Open `imprint.html` and replace all pink `[placeholder]` fields with real legal information.
3. **Set the Privacy Policy date:** Replace `[Placeholder — insert date before publishing]` in `privacy-policy.html` with the actual effective date.
4. **Add an OG image:** Place a 1200×630 px image at `assets/og-image.png` for social sharing previews.
5. **Add a favicon:** The SVG logo works as a favicon. For broad browser support, also add a 32×32 `favicon.ico`.

---

## Local Preview

No build step is required. Open any HTML file directly in a browser:

```bash
# Option 1: open directly
open index.html

# Option 2: serve with Python (recommended — avoids CORS issues with fonts)
python3 -m http.server 8000
# then open http://localhost:8000

# Option 3: use the VS Code Live Server extension and click "Go Live"
```

---

## Deployment

### GitHub Pages

1. Push the repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select the branch (`main`) and folder (`/ (root)`).
4. Click **Save**. GitHub Pages will deploy at `https://<username>.github.io/<repo>`.
5. For the custom domain, see the **Custom Domain** section below.

> To set the custom domain via file, create a file named `CNAME` in the repository root containing only:
> ```
> pinmuse.com
> ```

---

### Netlify

**Option A — Drag & drop:**
1. Go to [https://app.netlify.com](https://app.netlify.com).
2. Drag the entire project folder onto the Netlify dashboard.
3. Netlify deploys instantly and provides a temporary URL.

**Option B — Git integration:**
1. Connect your GitHub repository in the Netlify dashboard.
2. Set **Publish directory** to `/` (root) — no build command needed.
3. Click **Deploy site**.

For the custom domain:
- Go to **Site settings → Domain management → Add custom domain**.
- Enter `pinmuse.com` and follow the DNS instructions.

---

### Vercel

**Option A — CLI:**
```bash
npm install -g vercel   # one-time install
vercel                  # run from the project root
```

**Option B — Dashboard:**
1. Go to [https://vercel.com](https://vercel.com) and import your GitHub repository.
2. Leave **Framework Preset** as **Other** and **Build Command** empty.
3. Set **Output Directory** to `.` (current directory).
4. Click **Deploy**.

For the custom domain:
- Go to **Project → Settings → Domains**.
- Add `pinmuse.com` and follow the provided DNS instructions.

---

## Connecting the Custom Domain (pinmuse.com)

Regardless of hosting provider, update your DNS registrar with:

| Type  | Name | Value                                     |
|-------|------|-------------------------------------------|
| A     | @    | (IP provided by your hosting platform)   |
| CNAME | www  | (domain alias provided by your host)     |

Each platform provides the exact values in their domain setup wizard. DNS changes may take up to 24–48 hours to propagate.

**Always enable HTTPS** (all platforms do this automatically via Let's Encrypt).

---

## Pinterest Developer Submission

When submitting PinMuse to the Pinterest Developer portal, use the following:

| Field                 | Value                                         |
|-----------------------|-----------------------------------------------|
| **Website URL**       | https://pinmuse.com                           |
| **Privacy Policy URL**| https://pinmuse.com/privacy-policy.html       |
| **App Name**          | PinMuse                                       |
| **App Description**   | PinMuse helps users recreate Pinterest-inspired outfits using clothing from their own wardrobe with AI-powered styling and weather-aware recommendations. |

### Checklist for Pinterest Developer Review

- [x] Website is publicly accessible via HTTPS
- [x] Website is professional and clearly associated with the app
- [x] Privacy Policy page is live at `/privacy-policy.html`
- [x] Privacy Policy covers Pinterest data, AI services, and location
- [x] Site is hosted on a proper custom domain (`pinmuse.com`), not a social media profile
- [x] Pages load without errors (no broken links, no missing assets)
- [x] Pinterest disclaimer is present: "PinMuse is an independent application and is not affiliated with, endorsed by, or sponsored by Pinterest."
- [ ] Imprint placeholders replaced with real legal information
- [ ] Privacy Policy effective date filled in
- [ ] Logo replaced with production app icon

---

## Tech Stack

| Layer     | Technology              |
|-----------|-------------------------|
| Markup    | HTML5 (semantic)        |
| Styles    | CSS3 (custom properties, Grid, Flexbox) |
| Scripts   | Vanilla JS (none currently) |
| Fonts     | Google Fonts (Cormorant Garamond, Inter) via CDN |
| Hosting   | GitHub Pages / Netlify / Vercel |
| Backend   | None                    |
| Build     | None                    |

---

## License

© PinMuse. All rights reserved.
