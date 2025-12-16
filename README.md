# maxkagan.com

Personal academic website for Max Kagan, Postdoctoral Research Scholar at Columbia Business School.

## Files

```
├── index.html              # Home page
├── research.html           # Research papers
├── politics-at-work.html   # Politics at Work project page
├── cv.html                 # CV viewer
├── styles.css              # All styling
├── images/
│   └── headshot.jpg        # Profile photo
└── docs/
    └── KAGAN_CV.pdf        # CV document
```

## Setup Instructions

### 1. Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click **New repository** (green button)
3. Name it `maxkagan.github.io` (this naming enables GitHub Pages automatically)
4. Make it **Public**
5. Click **Create repository**

### 2. Upload Files

**Option A: GitHub Web Interface (easiest)**
1. In your new repo, click **uploading an existing file**
2. Drag all files and folders from this package
3. Click **Commit changes**

**Option B: Git Command Line**
```bash
git clone https://github.com/YOUR_USERNAME/maxkagan.github.io.git
cd maxkagan.github.io
# Copy all website files here
git add .
git commit -m "Initial website"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages** (left sidebar)
2. Under "Source", select **Deploy from a branch**
3. Select **main** branch and **/ (root)** folder
4. Click **Save**
5. Wait 1-2 minutes, then visit `https://YOUR_USERNAME.github.io`

### 4. Connect maxkagan.com (Squarespace Domain)

**Step A: Add custom domain in GitHub**
1. In repo **Settings** → **Pages**
2. Under "Custom domain", enter `maxkagan.com`
3. Click **Save**
4. Check "Enforce HTTPS" (after DNS propagates)

**Step B: Configure Squarespace DNS**

Log into Squarespace → Domains → maxkagan.com → DNS Settings

**Delete existing records** pointing to Google Sites, then add:

| Type | Host | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | YOUR_USERNAME.github.io |

**DNS propagation takes 15 minutes to 48 hours.** You can check status at [dnschecker.org](https://dnschecker.org).

### 5. Add Your CV

1. Export your CV as PDF
2. Name it `KAGAN_CV.pdf`
3. Upload to the `docs/` folder in your repo

## Making Updates

**Edit directly on GitHub:**
1. Navigate to the file you want to edit
2. Click the pencil icon (Edit)
3. Make changes
4. Click **Commit changes**

**Or edit locally:**
```bash
git pull
# Make edits
git add .
git commit -m "Description of changes"
git push
```

Changes go live within 1-2 minutes after committing.

## Adding New Papers

In `research.html`, copy an existing paper block and modify:

```html
<article class="paper-card surface-card">
    <div class="paper-content">
        <div class="paper-card-header">
            <span class="paper-label paper-label--working">Working Paper</span>
            <h3 class="paper-title">Your Paper Title</h3>
            <p class="paper-meta"><span class="paper-authors">Author, A., Author, B.</span></p>
            <p class="paper-description">
                One-sentence description of your paper.
            </p>
        </div>
        <div class="paper-actions">
            <div class="paper-action-group">
                <a class="btn btn-sm btn-outline-primary paper-action-link" href="SSRN_URL" target="_blank">
                    SSRN
                </a>
            </div>
            <button class="btn btn-sm btn-outline-primary paper-toggle" type="button" aria-expanded="false">
                <span class="paper-toggle-text">Show abstract</span>
                <span class="paper-toggle-icon"><i class="fas fa-chevron-down"></i></span>
            </button>
        </div>
        <div class="paper-abstract" hidden>
            <p>Full abstract text here.</p>
        </div>
    </div>
</article>
```

**Label options:**
- `paper-label--jmp` — Job Market Paper (gold)
- `paper-label--working` — Working Paper (purple)
- `paper-label--review` — Under Review (pink)
- `paper-label--published` — Published (green)

## Troubleshooting

**Site not loading?**
- Wait a few minutes after enabling GitHub Pages
- Check Settings → Pages for any error messages
- Ensure `index.html` is in the root directory

**Custom domain not working?**
- DNS takes up to 48 hours to propagate
- Verify A records point to GitHub's IPs exactly
- Make sure you deleted old DNS records pointing to Google Sites

**CSS not loading?**
- Check that `styles.css` exists in the root directory
- File paths are case-sensitive on GitHub Pages
