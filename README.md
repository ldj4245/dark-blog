# Dark Blog with Netlify CMS

A dark-themed blog with integrated Netlify CMS for web-based content management.

## Features

- 🌙 Dark theme design
- ✍️ Web-based content management with Netlify CMS
- 🔐 GitHub authentication for secure access
- 📝 Markdown support with live preview
- 🚀 GitHub Pages deployment
- 📱 Responsive design

## Setup Instructions

### 1. Repository Setup

The repository is already configured with:
- `admin/index.html` - Netlify CMS interface
- `admin/config.yml` - CMS configuration
- `_posts/` directory for blog posts
- Main `index.html` with admin button

### 2. Netlify CMS Authentication Setup

To enable GitHub authentication for Netlify CMS, you need to set up OAuth:

#### Option A: Using Netlify (Recommended)
1. Deploy your site to Netlify
2. Go to Netlify Dashboard → Site Settings → Access Control
3. Under "OAuth", click "Install provider"
4. Select "GitHub" and authorize
5. Netlify will automatically handle the authentication

#### Option B: Using GitHub OAuth App
1. Go to GitHub Settings → Developer settings → OAuth Apps
2. Click "New OAuth App"
3. Fill in:
   - **Application name**: `Dark Blog CMS`
   - **Homepage URL**: `https://yourusername.github.io/dark-blog`
   - **Authorization callback URL**: `https://api.netlify.com/auth/done`
4. After creating, note down the **Client ID** and **Client Secret**
5. Add these to your Netlify site environment variables

### 3. GitHub Pages Setup

1. Go to Repository Settings → Pages
2. Under "Source", select "Deploy from a branch"
3. Choose "main" branch and "/ (root)"
4. Your site will be available at `https://yourusername.github.io/dark-blog`

### 4. Using the CMS

1. Visit your blog site: `https://yourusername.github.io/dark-blog`
2. Click the "글쓰기 (Admin)" button in the top-right corner
3. You'll be redirected to `/admin/` - the Netlify CMS interface
4. Click "Login with GitHub" to authenticate
5. Once logged in, you can:
   - Create new posts
   - Edit existing posts
   - Upload images
   - Preview changes
   - Publish directly to the repository

## File Structure

```
dark-blog/
├── admin/
│   ├── index.html          # Netlify CMS interface
│   └── config.yml          # CMS configuration
├── _posts/                 # Blog posts directory
│   └── 2025-09-04-sample-post.md
├── assets/
│   └── images/            # Image uploads (created automatically)
├── index.html             # Main blog page
└── README.md              # This file
```

## Configuration Details

### CMS Configuration (`admin/config.yml`)
- **Backend**: git-gateway (works with GitHub)
- **Media folder**: `assets/images`
- **Collections**: Posts with markdown support
- **Fields**: Title, date, tags, and body content

### Post Format
Posts should follow Jekyll front matter format:
```yaml
---
layout: post
title: "Your Post Title"
date: 2025-09-04
tags: ["tag1", "tag2"]
---

# Your content here
```

## Customization

### Adding New Content Types
Edit `admin/config.yml` to add new collections (pages, projects, etc.)

### Styling
Modify the CSS in `index.html` to customize the theme

### CMS Interface
Customize the CMS by editing `admin/config.yml` fields and widgets

## Troubleshooting

### CMS Not Loading
- Check that `admin/index.html` and `admin/config.yml` are in place
- Verify GitHub Pages is enabled
- Ensure the site URL is correct in OAuth settings

### Authentication Issues
- Verify OAuth app settings
- Check Netlify authentication configuration
- Ensure callback URLs match exactly

### Posts Not Appearing
- Check that posts are in `_posts/` directory
- Verify front matter format
- Ensure file names follow `YYYY-MM-DD-title.md` pattern

## Support

For issues related to:
- **Netlify CMS**: [Netlify CMS Documentation](https://www.netlifycms.org/docs/)
- **GitHub Pages**: [GitHub Pages Documentation](https://docs.github.com/en/pages)
- **Jekyll**: [Jekyll Documentation](https://jekyllrb.com/docs/)

## License

This project is open source and available under the [MIT License](LICENSE).
