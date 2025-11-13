# Content Management System Guide

## Overview

Your site now includes **Decap CMS** - a mobile-friendly, browser-based content management system that lets you add and edit pages from any device.

## Accessing the CMS

### From Desktop or Mobile Browser:
1. Visit: `https://pennyphilosopher.com/admin`
2. Click "Login with GitHub"
3. Authorize the application (first time only)
4. Start editing!

## Features

### ✅ Add/Edit Pages
- Create new pages through the CMS interface
- Edit existing content with a rich text editor
- Preview changes before publishing
- Add images and media

### ✅ Mobile-Friendly
- Works on any mobile browser (Chrome, Safari, Firefox)
- No app installation required
- Responsive interface optimized for touch

### ✅ Automatic Deployment
- Changes are saved to your GitHub repository
- GitHub Actions automatically deploys updates
- Live within 2-3 minutes of publishing

## How to Use

### Creating a New Page:
1. Go to `/admin`
2. Click "Pages" in the sidebar
3. Click "New Page"
4. Fill in:
   - Title
   - Date
   - Description (optional)
   - Body content (use Markdown)
   - Featured image (optional)
5. Click "Save" (saves as draft)
6. Click "Publish" when ready to go live

### Editing an Existing Page:
1. Go to `/admin`
2. Click "Pages" in the sidebar
3. Select the page you want to edit
4. Make your changes
5. Click "Save" then "Publish"

### Editorial Workflow:
- **Draft**: Save work in progress
- **In Review**: Mark for review before publishing
- **Ready**: Approved and ready to publish
- **Published**: Live on the site

## Site Structure

```
/
├── index.html          # Home page
├── chatbot.html        # Idea Explorer tool
├── admin/              # CMS interface
│   ├── index.html
│   └── config.yml
├── content/            # CMS-managed content
│   ├── pages/          # Your pages (Markdown)
│   └── settings/       # Site settings
└── images/             # Uploaded media
```

## Mobile Editing Workflow

1. Open your mobile browser
2. Navigate to `pennyphilosopher.com/admin`
3. Login with GitHub (saved for future sessions)
4. Edit or create content
5. Publish when done
6. Changes go live automatically!

## Tips

- **Markdown Support**: Use Markdown for formatting (headings, lists, links, etc.)
- **Image Uploads**: Upload images directly through the CMS
- **Preview**: Use the preview pane to see how content will look
- **Drafts**: Save drafts to work on content over multiple sessions
- **Mobile Editing**: Best experience on tablets and phones with landscape orientation

## Authentication

The CMS uses GitHub OAuth for authentication. You need:
- A GitHub account
- Contributor access to the repository
- One-time authorization when you first login

## Troubleshooting

### Can't login?
- Ensure you have access to the GitHub repository
- Check that you've authorized the OAuth app
- Try clearing browser cache and logging in again

### Changes not appearing?
- Wait 2-3 minutes for deployment to complete
- Check GitHub Actions tab for deployment status
- Ensure you clicked "Publish" (not just "Save")

### Mobile issues?
- Use a modern browser (Chrome, Safari, Firefox)
- Ensure stable internet connection
- Try landscape orientation for better layout

## Support

For issues or questions:
- Check GitHub repository issues
- Review Decap CMS documentation: https://decapcms.org/docs/
- Verify GitHub Actions deployment logs

---

**Ready to start editing?** Visit [/admin](/admin) now!
