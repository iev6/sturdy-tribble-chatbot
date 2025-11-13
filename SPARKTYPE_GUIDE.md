# Sparktype CMS Integration Guide

## Overview

This site uses **Sparktype** - a browser-based publishing platform that combines the ease of use of a CMS with the performance of a static site generator.

**Official Site:** [app.sparktype.org](https://app.sparktype.org)
**Project:** [github.com/sparktype-project/sparktype](https://github.com/sparktype-project/sparktype)

---

## What is Sparktype?

Sparktype is designed with three core principles:

1. **Simplicity** - Content-first approach with pure HTML/CSS output (minimal JavaScript)
2. **Security** - Static sites require no maintenance or security updates
3. **Usability** - Simple editing interface that handles technical complexity for you

### Key Features

- ✅ Browser-based editor (works on mobile and desktop)
- ✅ No installation required
- ✅ Runs locally in your browser (your data stays private)
- ✅ Exports clean, static HTML/CSS
- ✅ No tracking by default
- ✅ Can be hosted anywhere

---

## Important: GitHub Branch Setup

**Note:** Sparktype may try to import from the `master` branch by default. This repository uses `main`.

If you get an import error, you need to either:
1. **Create a master branch alias** (recommended):
   ```bash
   git checkout main
   git branch master
   git push origin master
   ```
2. **Or** wait for Sparktype to add main branch support

## How to Use Sparktype with This Repository

### Method 1: Import from GitHub (After Merge to Main)

1. **Ensure Changes Are Merged**
   - Merge this branch to `main`
   - Ensure `_site/manifest.json` is present
   - Push to GitHub

2. **Import into Sparktype**
   - Visit [app.sparktype.org](https://app.sparktype.org)
   - Click "Import from GitHub"
   - Enter: `iev6/sturdy-tribble-chatbot`
   - Select branch: `main` (or `master` if you created the alias)

3. **Edit and Export**
   - Edit your content in Sparktype
   - Export when done

### Method 2: Create New Site in Sparktype (Easier)

1. **Open Sparktype**
   - Visit [app.sparktype.org](https://app.sparktype.org) in your browser
   - Create a new site or import existing content

2. **Create/Edit Content**
   - Use the visual editor to create pages
   - Add text, images, and formatting
   - Organize your content with collections

3. **Export Your Site**
   - Click the export/download button
   - Your site will download as a ZIP file

4. **Deploy to GitHub**
   ```bash
   # Extract the ZIP file
   unzip sparktype-export.zip -d temp-site

   # Copy content to your repository
   # Option 1: Replace entire pages directory
   rm -rf pages/*
   cp -r temp-site/* pages/

   # Option 2: Merge with existing content
   cp -r temp-site/* pages/

   # Commit and push
   git add pages/
   git commit -m "Update content via Sparktype"
   git push origin main
   ```

5. **Automatic Deployment**
   - GitHub Actions will automatically deploy your changes
   - Your site will be live in 2-3 minutes!

### Mobile Workflow

#### Editing on Mobile:
1. Open your mobile browser (Safari, Chrome, Firefox)
2. Navigate to [app.sparktype.org](https://app.sparktype.org)
3. Create or edit your content
4. Export when finished

#### Deploying from Mobile:
Since GitHub doesn't have great mobile support for uploading files, you have a few options:

**Option A: Use GitHub Mobile App**
1. Download your Sparktype export
2. Extract the ZIP (use Files app on iOS or a file manager on Android)
3. Use GitHub Mobile app to upload files (limited, but works for small changes)

**Option B: Wait Until Desktop**
1. Export and save to cloud storage (Google Drive, iCloud, Dropbox)
2. Upload to GitHub when you're back at a desktop

**Option C: Use Working Copy (iOS)**
1. Install Working Copy app (Git client for iOS)
2. Clone your repository
3. Extract Sparktype export to the repository
4. Commit and push from Working Copy

**Option D: GitHub Web Interface**
1. Go to github.com on mobile browser
2. Navigate to your repository
3. Upload files one at a time (tedious but works)

---

## Repository Structure

```
/
├── index.html              # Homepage (custom)
├── chatbot.html           # Idea Explorer tool (custom)
├── pages/                 # Sparktype-generated content
│   ├── [your-pages.html]
│   └── assets/
│       ├── css/
│       └── images/
├── images/                # Additional media
└── favicon.ico
```

### Important Notes:

- Keep your custom files (`index.html`, `chatbot.html`) in the root
- Put Sparktype-exported content in `/pages`
- This separates your custom interactive tools from CMS content

---

## Tips & Best Practices

### Content Organization

1. **Use Collections** - Organize related pages in Sparktype collections
2. **Consistent Naming** - Use clear, URL-friendly page names
3. **Backup Exports** - Keep copies of your Sparktype exports

### Image Management

- Upload images through Sparktype's editor
- Images will be included in your export
- Sparktype optimizes images automatically

### Version Control

```bash
# Always pull before making changes
git pull origin main

# Check what changed
git status
git diff

# Commit with descriptive messages
git commit -m "Add new blog post about X"
git commit -m "Update homepage content"
git commit -m "Fix typo in about page"
```

### Keeping Custom Features

This repository has custom features (like the Idea Explorer). To preserve them:

1. **Never overwrite root files** - Keep `index.html` and `chatbot.html` as-is
2. **Use the /pages directory** - Put all Sparktype content there
3. **Update navigation carefully** - If you change navigation, update both custom pages

---

## Troubleshooting

### "Export doesn't include my images"
- Make sure images are uploaded through Sparktype's editor
- Images linked from external URLs won't be included in the export

### "Site looks broken after deployment"
- Check file paths in your exported HTML
- Ensure all assets are in the `/pages` directory
- Verify GitHub Pages is enabled and deploying from `main` branch

### "Can't access Sparktype on mobile"
- Sparktype works in mobile browsers
- Use landscape mode for better experience
- Some features may be limited on very small screens

### "Export is too large for GitHub"
- GitHub has file size limits (100MB per file, repository size limits)
- Optimize images before adding to Sparktype
- Consider hosting large media files elsewhere

---

## Automatic Deployment

This repository is configured with GitHub Actions for automatic deployment:

- **Trigger**: Push to `main` branch
- **Process**: GitHub Actions builds and deploys to GitHub Pages
- **Time**: ~2-3 minutes
- **URL**: https://pennyphilosopher.com

### Deployment Workflow:

```yaml
# .github/workflows/static.yml
# Automatically deploys on every push to main
```

You don't need to do anything special - just push your changes!

---

## Advanced: Customizing Sparktype Themes

Sparktype uses a theming system. You can:

1. Customize themes in the Sparktype editor
2. Edit CSS files in your exported `/pages/assets/css/` directory
3. Create custom themes (see Sparktype documentation)

---

## Resources

- **Sparktype App**: [app.sparktype.org](https://app.sparktype.org)
- **Sparktype GitHub**: [github.com/sparktype-project/sparktype](https://github.com/sparktype-project/sparktype)
- **Your Repository**: [github.com/iev6/sturdy-tribble-chatbot](https://github.com/iev6/sturdy-tribble-chatbot)
- **Live Site**: [pennyphilosopher.com](https://pennyphilosopher.com)

---

## Quick Reference

### Common Commands

```bash
# Clone repository
git clone https://github.com/iev6/sturdy-tribble-chatbot.git

# Pull latest changes
git pull origin main

# Add all changes
git add .

# Commit changes
git commit -m "Your message here"

# Push to deploy
git push origin main

# Check status
git status

# View deployment logs
# Go to: https://github.com/iev6/sturdy-tribble-chatbot/actions
```

### File Structure Quick Guide

- `index.html` - Homepage (don't overwrite)
- `chatbot.html` - Idea Explorer (don't overwrite)
- `pages/` - Sparktype content (safe to replace)
- `images/` - Additional media
- `.github/workflows/` - Deployment config (don't modify)

---

## Need Help?

- **Sparktype Issues**: [github.com/sparktype-project/sparktype/issues](https://github.com/sparktype-project/sparktype/issues)
- **This Repository**: Create an issue in your repo

---

**Happy publishing! 🚀**
