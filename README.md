# Colectivo Costero Website

Hugo-based website for Colectivo Costero nonprofit organization. Clean, fast, and focused on donations and community impact.

## Quick Start

### Prerequisites
- Hugo v0.87+ (install from https://gohugo.io/installation/)
- Git (for deployment)

### Local Development

```bash
# Clone this repo
git clone [your-repo-url]
cd colectivo-costero

# Run local server
hugo server

# Visit http://localhost:1313
```

Site will hot-reload as you edit content.

### Building for Production

```bash
hugo
# Output in /public directory
```

## Project Structure

```
colectivo-costero/
├── content/           # Page content (Markdown)
│   ├── _index.md      # Homepage
│   ├── about.md       # About page
│   ├── donate.md      # Donation page
│   ├── projects/      # Projects page + individual projects
│   └── partners/      # Partners page
├── themes/colectivo/  # Custom theme
│   ├── layouts/       # HTML templates
│   └── static/        # CSS and assets
├── hugo.toml          # Site configuration
└── netlify.toml       # Netlify deployment config
```

## Content Management

### Adding a New Page

1. Create a Markdown file in `content/`
2. Add front matter with title and metadata
3. Add your content below

Example:
```markdown
---
title: "Page Title"
description: "Short description"
---

# Page Title

Your content here...
```

### Editing Existing Pages

All content is in `content/` directory. Edit the `.md` files directly.

## Zeffy Integration

The site is configured for Zeffy donation forms.

### Add Zeffy Donation Forms

1. Get your Zeffy fundraiser embed code from Zeffy
2. In `content/donate.md`, replace the donation links:
   - Find: `https://[zeffy-link]`
   - Replace with your actual Zeffy donation URL

### Alternative: Embed Zeffy Widget

For embedded donation form instead of link:

```html
<zeffy-fundraiser-embed id="YOUR-FUNDRAISER-ID"></zeffy-fundraiser-embed>
```

The page already has Zeffy scripts loaded in the template.

## Deployment

### Option 1: Deploy to Netlify (Recommended)

1. Push code to GitHub/GitLab
2. Connect repo to Netlify at https://app.netlify.com
3. Build settings:
   - Build command: `hugo`
   - Publish directory: `public`
4. Deploy!

Netlify will auto-build on every push.

### Option 2: Manual Deployment

1. Run `hugo` to build
2. Upload contents of `public/` folder to your hosting provider
3. Point domain to your hosting

## Domain Transfer

To move from Wix to this site:

1. Update DNS records to point to your hosting provider
2. Set up a redirect from old site to new (ask your Wix support)
3. Update domain in `hugo.toml` if needed

## Customization

### Colors

Edit theme colors in `themes/colectivo/static/css/style.css`:

```css
:root {
    --primary: #1E88A8;      /* Main blue */
    --secondary: #4A90E2;    /* Light blue */
    --accent: #E74C3C;       /* Red */
}
```

### Logo/Branding

- Logo text: Edit in `themes/colectivo/layouts/partials/header.html`
- Add logo image: Place in `themes/colectivo/static/images/` and reference in header

### Contact Info

Update in `hugo.toml`:
- Email, phone, address, EIN, etc.

All are used in footer and contact pages automatically.

## Support & Maintenance

### Regular Updates

- Edit content in `content/` directory
- Push changes to trigger auto-rebuild
- No technical knowledge needed once deployed

### Troubleshooting

**Site not loading?**
- Check Netlify deploy logs
- Run `hugo` locally to test

**Navigation broken?**
- Check `hugo.toml` menu configuration
- Ensure all pages have correct titles

**Need help?**
- Contact Netlify support if deployment issues
- Test locally with `hugo server` first

## Analytics & Tracking

To add Google Analytics or other tracking:

1. Get your tracking ID
2. Add to `hugo.toml`:
   ```toml
   [params]
     googleAnalyticsID = "G-YOUR-ID"
   ```
3. Update `themes/colectivo/layouts/baseof.html` to include tracking script

## License

Content © Colectivo Costero. Theme available under MIT License.

---

**Next Steps:**
1. Get Hugo running locally
2. Test the site with `hugo server`
3. Connect to Netlify for auto-deployment
4. Add Zeffy donation links
5. Point domain to Netlify
