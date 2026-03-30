# Deploy carbonandchrome.io — Landing Page

## Option 1: Netlify (Fastest — 2 minutes)

1. Go to https://app.netlify.com
2. Sign up / log in with GitHub
3. Drag and drop the `company-site` folder onto the Netlify dashboard
4. It deploys instantly with a random URL like `random-name.netlify.app`
5. Go to **Domain settings** → **Add custom domain** → `carbonandchrome.io`
6. Netlify gives you DNS records to add in Namecheap:
   - Type: CNAME, Host: www, Target: your-site.netlify.app
   - Type: A, Host: @, Target: 75.2.60.5 (Netlify's IP)
7. Enable HTTPS (free, automatic with Let's Encrypt)
8. Done — carbonandchrome.io is live

## Option 2: Cloudflare Pages (Also Free)

1. Go to https://dash.cloudflare.com
2. Pages → Create project → Upload assets
3. Upload the `company-site` folder
4. Add custom domain: carbonandchrome.io
5. Transfer DNS to Cloudflare (or add CNAME records in Namecheap)

## Option 3: GitHub Pages (Free, Git-based)

1. Create a repo: `carbonandchrome/carbonandchrome.io`
2. Push the index.html
3. Settings → Pages → Deploy from main branch
4. Custom domain: carbonandchrome.io
5. Add DNS records in Namecheap:
   - A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - CNAME: www → carbonandchrome.github.io

## For Stripe Verification

Stripe needs to see:
- Company name on the website ✅ (Carbon & Chrome Holdings LLC)
- Products/services described ✅ (CC Themes, Neoadis OS, Chrome Life)
- Contact info ✅ (hello@carbonandchrome.org)
- Physical location ✅ (Virginia, USA)
- Terms of service (add /terms.html if Stripe asks)
- Privacy policy (add /privacy.html if Stripe asks)

## Files
- `index.html` — the landing page (single file, no dependencies)
