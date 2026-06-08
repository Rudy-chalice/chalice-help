# Chalice Help Center (MkDocs Material)

A free, Chalice-branded help center built with MkDocs Material and hosted on Cloudflare Pages.

## What's here

- `mkdocs.yml` - site config, navigation, and theme
- `requirements.txt` - the one dependency (mkdocs-material)
- `docs/` - all content. Each `.md` file is a page.
- `docs/index.md` - the homepage with the category tiles
- `docs/stylesheets/extra.css` - Chalice colors (black + gold)

## How to add or edit an article (no command line)

1. Go to your repo on GitHub.
2. Open the `docs/` folder and the section you want (for example `the-trade-desk`).
3. Click **Add file > Create new file**, name it something like `accepting-a-deal.md`, and write in Markdown.
4. Add the new page to the `nav:` list in `mkdocs.yml` so it shows in the menu.
5. Commit. Cloudflare rebuilds the site automatically in about a minute.

## Deploy steps (one time)

### 1. Create a GitHub account and repo
- Sign up at github.com (free).
- Create a new repository named `chalice-help`.
- Use **Add file > Upload files** and drag in everything from this folder (mkdocs.yml, requirements.txt, the docs folder). Commit.

### 2. Create a Cloudflare account and connect Pages
- Sign up at cloudflare.com (free).
- Go to **Workers & Pages > Create > Pages > Connect to Git**.
- Authorize GitHub and pick the `chalice-help` repo.
- Set the build settings:
    - **Build command:** `pip install -r requirements.txt && mkdocs build`
    - **Build output directory:** `site`
    - If the build fails on Python, add an environment variable `PYTHON_VERSION` = `3.12`.
- Save and Deploy. You'll get a free `your-project.pages.dev` URL.

### 3. (Optional) Use your own domain
- In the Pages project, go to **Custom domains** and add `help.chalice.ai`.
- This needs access to Chalice's DNS to add the record Cloudflare gives you.

## Branding notes

- Colors live in `docs/stylesheets/extra.css`. Gold is `#c9a24b`, black is `#0b0b0b`.
- To use the real Chalice logo, drop a `logo.png` into `docs/assets/` and add `logo: assets/logo.png` under `theme:` in `mkdocs.yml` (replacing the `icon: logo:` line).
