# QAlive Blog (`blog.qalive.online`)

Dedicated standalone blog for [QAlive](https://qalive.online), powered by Astro, Tailwind CSS, and Notion Headless CMS.

## Features
- **Clean Medium-style feed**: Centered, distraction-free reading experience without thumbnails or cluttered sidebars.
- **Dynamic Topic Filtering**: Interactive tabs (`All`, `Product`, `Guides`, `Announcements`) populated dynamically from Notion.
- **Clean Subdomain URLs**: Served directly at the root (`https://blog.qalive.online/` and `https://blog.qalive.online/:slug`).
- **Headless Notion CMS**: Real-time article retrieval and publishing from Notion.
- **Optimized for SEO**: Auto-generated sitemaps, OpenGraph metadata, JSON-LD Schema (`BlogPosting`), and robots.txt.

---

## Deployment on Cloudflare Pages (Step-by-step)

### 1. Create a GitHub repository
Create a new private or public repository on GitHub (e.g. `qalive-blog`) and push this project:
```bash
git remote add origin git@github.com:ChrisCoolDev/qalive-blog.git
git branch -M main
git push -u origin main
```

### 2. Connect to Cloudflare Pages
1. Go to your **Cloudflare Dashboard** → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**.
2. Select your `qalive-blog` repository.
3. Configure build settings:
   - **Framework preset**: `Astro`
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
4. Add **Environment Variables** in Cloudflare Pages:
   - `NOTION_SECRET`: Your Notion secret key (`ntn_...`)
   - `NOTION_BLOG_DATABASE_ID`: `40e8dd6204eb80f386d5fd7c2764b74f`
5. Click **Save and Deploy**.

### 3. Add Custom Domain (`blog.qalive.online`)
1. In Cloudflare Pages, go to **Custom domains** tab.
2. Click **Set up a custom domain**.
3. Enter `blog.qalive.online`.
4. Cloudflare automatically sets up the DNS CNAME record for you with SSL enabled.

