# David Campbell - Personal Website

Professional website for David Campbell, Engineering Leader and AI Security Expert.

## Overview

This is a single-page static website built with vanilla HTML and Tailwind CSS (via CDN). The site showcases:

- AI Security & Red Teaming expertise
- Engineering Leadership experience
- Speaking engagements and thought leadership
- Professional achievements and recognition
- Contact information for consulting/advisory opportunities

## Technology Stack

- **HTML5** - Semantic markup
- **Tailwind CSS** - Utility-first CSS framework (loaded via CDN)
- **JavaScript** - Vanilla JS for smooth scrolling and navigation
- **Google Fonts** - Inter font family

## Local Development

Simply open `index.html` in your browser:

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Or just open the file directly
open index.html
```

Then navigate to `http://localhost:8000` in your browser.

## Deployment Options

### Option 1: Netlify (Recommended)

1. Create a free account at [netlify.com](https://netlify.com)
2. Drag and drop the `mrcampbell.org` folder to Netlify
3. Configure custom domain:
   - Go to Domain Settings
   - Add custom domain: `mrcampbell.org`
   - Follow DNS configuration instructions

**OR** use Netlify CLI:

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
cd mrcampbell.org
netlify deploy --prod
```

### Option 2: Vercel

1. Install Vercel CLI:
```bash
npm install -g vercel
```

2. Deploy:
```bash
cd mrcampbell.org
vercel --prod
```

3. Configure custom domain in Vercel dashboard

### Option 3: GitHub Pages

1. Create a new GitHub repository
2. Push this folder to the repository:
```bash
cd mrcampbell.org
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/mrcampbell.org.git
git push -u origin main
```

3. Enable GitHub Pages:
   - Go to repository Settings > Pages
   - Source: Deploy from a branch
   - Branch: main / root
   - Save

4. Configure custom domain in repository settings

### Option 4: AWS S3 + CloudFront

1. Create S3 bucket:
```bash
aws s3 mb s3://mrcampbell.org
```

2. Upload files:
```bash
aws s3 sync . s3://mrcampbell.org --acl public-read
```

3. Enable static website hosting:
```bash
aws s3 website s3://mrcampbell.org --index-document index.html
```

4. (Optional) Set up CloudFront for HTTPS and better performance

### Option 5: Cloudflare Pages

1. Create a Cloudflare account
2. Go to Pages > Create a project
3. Connect your git repository or upload directly
4. Configure custom domain in Cloudflare dashboard

## Domain Configuration

After deploying, configure your DNS records for `mrcampbell.org`:

**For Netlify:**
- Add A record: `75.2.60.5`
- Or CNAME: `your-site.netlify.app`

**For Vercel:**
- Add CNAME: `cname.vercel-dns.com`

**For GitHub Pages:**
- Add A records:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`

**For Cloudflare Pages:**
- DNS automatically configured if using Cloudflare as your registrar

## Customization

To update content, edit `index.html`:

1. **Contact Information** - Update email, phone, LinkedIn URL
2. **Professional Experience** - Modify experience section dates and descriptions
3. **Expertise Areas** - Adjust the four main focus areas
4. **Achievements** - Update recognition timeline
5. **Colors** - Change Tailwind color classes (e.g., `bg-blue-600` to `bg-purple-600`)

## File Structure

```
mrcampbell.org/
├── index.html          # Main website file
└── README.md           # This file
```

## Performance Optimization

For production, consider:

1. **Self-hosting Tailwind**: Use Tailwind CLI to generate a minimal CSS file
2. **Image optimization**: Add optimized images for hero section
3. **Analytics**: Add Google Analytics or Plausible
4. **SEO**: Already includes meta tags, consider adding:
   - Open Graph tags for social sharing
   - JSON-LD structured data
   - Sitemap.xml

## SEO Checklist

- [x] Semantic HTML structure
- [x] Meta description
- [x] Descriptive title tag
- [x] Heading hierarchy (H1, H2, H3)
- [ ] Add Open Graph meta tags
- [ ] Add Twitter Card meta tags
- [ ] Create sitemap.xml
- [ ] Add robots.txt
- [ ] Submit to Google Search Console

## Browser Support

Works on all modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

All content &copy; 2025 David Campbell. All rights reserved.

## Contact

David Campbell
- Email: david@mrcampbell.org
- LinkedIn: [linkedin.com/in/ddcam](https://linkedin.com/in/ddcam)
- Phone: +1 (408) 385-5300
