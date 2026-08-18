# Unbiased Consulting — Site + Blog

Static site (homepage) + Jekyll blog + Decap CMS admin dashboard.
No server, no database, no monthly software cost.

## What's in here

- `index.html` — your homepage (unchanged design, blog teasers now link to real posts)
- `blog/index.html` — blog listing page (auto-generated from `_posts/`)
- `_posts/` — your blog posts, as markdown files with a title/date/excerpt at the top
- `_layouts/` — the templates that wrap every post and the blog index in your site's design
- `admin/` — the login dashboard (Decap CMS) where you'll write new posts
- `assets/` — shared stylesheet and images

## Adding images

Drop image files straight into `assets/images/` — nothing else to configure.

- **New blog posts** (via the `/admin/` dashboard): just upload the cover image in the post form — it's placed here automatically and wired up for you.
- **Homepage photo:** save Parul's photo as `assets/images/parul-portrait.jpg` — the homepage already looks for this exact filename.
- **Homepage blog teasers** (the 3 featured posts on the homepage itself): save images as
  - `assets/images/blog-founder-led-marketing.jpg`
  - `assets/images/blog-fractional-cmo-vs-full-time.jpg`
  - `assets/images/blog-livon-turnaround.jpg`

Until an image is uploaded, each spot shows a plain text placeholder instead of a broken image — so the site never looks broken, it just quietly picks up the photo the moment you add it (same filename, any time).

## One-time setup (~20 minutes)

1. **Create a GitHub account** (if you don't have one) and a new repository — upload this whole folder to it.

2. **Deploy to Netlify:**
   - Sign up at netlify.com, click "Add new site" → "Import an existing project"
   - Connect your GitHub repo — Netlify will detect Jekyll automatically
   - Click Deploy. You'll get a live `*.netlify.app` URL within a minute.

3. **Connect your domain:**
   - In Netlify: Site settings → Domain management → Add domain → `parulbudhiraja.com`
   - Update the DNS records at wherever the domain is registered, as Netlify instructs (don't touch existing MX/email records)

4. **Turn on the login system (Netlify Identity):**
   - In Netlify: Site settings → Identity → Enable Identity
   - Under Registration, set to "Invite only" (so random people can't sign up)
   - Enable Git Gateway (Identity → Services → Git Gateway) — this lets the CMS save posts back to GitHub on your behalf
   - Under Identity → Invite users, invite yourself with your email

5. **Log in:**
   - Go to `parulbudhiraja.com/admin/`
   - Accept the invite email, set a password
   - You'll land on a dashboard with "Blog Posts" — click "New Blog Posts" to write, and "Publish" when ready. It goes live in about a minute.

## Writing a post from the dashboard

Once logged in at `/admin/`, you get a form: Title, Category, Publish Date, Cover Image, Excerpt, and a rich-text Body editor — no code involved. Publishing creates the markdown file and rebuilds the site automatically.

## If you'd rather not touch GitHub/Netlify yourself

This whole setup (steps 1–4) is a one-time job — happy to walk through it live with you, or you can hand this README to any developer/freelancer and it's about a 20-minute task for them.
