# Aathila Thasneem — Personal Site

Personal site and blog for Aathila Thasneem, M.Sc. Microbiology · Chennai.
Hosted on GitHub Pages: **https://moarshy.github.io/aathila/**

Source for what was previously at sciencesavvy3.wordpress.com.

## Stack

- **Astro** static site
- **Tailwind CSS v4** for styling
- **Decap CMS** for visual editing (at `/admin`)
- **GitHub Pages** for hosting
- **GitHub Actions** for auto-deploy on push to `main`

## Project layout

```
.
├── public/
│   ├── admin/                # Decap CMS — visit /admin/ to log in & edit posts
│   ├── images/
│   │   ├── posts/            # Hero images for blog posts
│   │   └── aathila-portrait.jpg
│   └── favicon.svg
├── src/
│   ├── components/           # Header, Footer, PostCard, FeaturedPost
│   ├── content/posts/        # Blog posts as markdown
│   ├── layouts/              # BaseLayout, PostLayout
│   ├── pages/                # Home, /writing, /about, /research, /cv, /contact
│   └── styles/global.css     # Theme: palette, fonts, prose styles
├── docs/                     # Source CV PDF
├── astro.config.mjs
└── .github/workflows/        # CI deploy to GitHub Pages
```

## Local development

```bash
nvm use 22
npm install
npm run dev          # http://localhost:4321/aathila/
npm run build        # Outputs to ./dist/
```

## Writing a new post

**Option A — through the CMS (no code):**
1. Go to `https://moarshy.github.io/aathila/admin/`
2. Log in with GitHub (requires the OAuth setup below)
3. Click **Posts → New Post**, fill in the fields, upload a hero image, write the body
4. Hit **Publish** → it commits to the repo → GitHub Actions deploys

**Option B — by editing markdown directly:**
- Add a new `.md` file to `src/content/posts/`
- Front-matter fields: `title`, `description`, `date`, `category` (`Science` | `Personal`), `tags`, `heroImage`, `heroAlt`, `heroCredit`, `featured`, `draft`
- Commit, push, done.

## CMS authentication (one-time setup)

Decap CMS needs to authenticate with GitHub to commit posts. Easiest free path:

1. Create a Netlify account at https://app.netlify.com (free)
2. Create a new site (any blank one) — we only need the Identity feature
3. In **Site settings → Identity → Services**, enable Git Gateway and point it at this repo
4. Alternatively: deploy a tiny OAuth proxy following [Decap's docs](https://decapcms.org/docs/external-oauth-clients/) — or use [decapbridge.com](https://decapbridge.com) (paid).

Until OAuth is set up, you can still edit posts by committing markdown directly to the repo.

## Deployment

1. The repo is at `moarshy/aathila`.
2. Push this directory to it: `git push -u origin main`
3. Repo → **Settings → Pages** → Source: **GitHub Actions**
4. Wait for the Actions workflow to finish (~1–2 minutes)
5. Site is live at `https://moarshy.github.io/aathila/`

## Design system

- **Brand:** Aathila Thasneem · The Cultured Crew (blog name lives in the /writing section)
- **Palette:** Soft scientific — `#f5f7fa` canvas · `#0f1e3d` navy ink · `#2dd4bf` mint/teal accent · `#fbcfe8` warm blush
- **Type:** Fraunces (display) + Inter (body)
- **Layout:** Magazine/editorial — large hero, post grid, photo-led

## Content migrated

All three original WordPress posts were migrated verbatim from sciencesavvy3.wordpress.com:

1. The Unconventional Choice — *Personal* (2025-01-13)
2. The Secret Ingredients in Your Milk — *Science* (2025-01-11, featured)
3. Evening Reflections — *Personal* (2025-01-10)
