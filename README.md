# Appliance Repair Help

Static directory site (Python + Markdown) for washer, dryer, refrigerator, and dishwasher repair help. Brand: Black Swan Sibyl (Christie Justice). Timezone: America/Chicago.

**Live site:** https://appliance.christiejustice.com (GitHub Pages, repo `christieMogulReport/appliance-repair-directory`). `static/CNAME` holds the custom domain and `base_url` in `config.yml` matches it.

## Commands
```bash
python3 build.py            # build into dist/ (drafts excluded)
python3 serve.py            # build and preview at http://127.0.0.1:8000
python3 build.py --drafts   # include draft: true pages
```
The first run creates a local `.venv` and installs `requirements.txt`.

## Add a page
Create `content/pages/<slug>.md` with front matter: `title`, `slug`, `description`, `last_updated` (YYYY-MM-DD), optional `draft`, optional `listings` (each with `name`, `url`, optional `affiliate_url`, `summary`, `category`). Quote any value containing a colon. Homepage intro is `content/home.md`; site settings are `config.yml`.

## Rules for content
- Niche is locked: washers, dryers, refrigerators, dishwashers. Do not drift to other topics.
- Only real, sourced information. Prices and costs only with a linked source. Verify every URL (drop 404s). Give safety steps first (unplug, shut off water).
- No invented numbers or listings.
- Before adding an affiliate link, make sure `affiliate_disclosure` in `config.yml` is accurate.

## Deploy
Pushing to `main` runs `.github/workflows/pages.yml`, which installs `requirements.txt`, runs `python build.py`, and deploys `dist/` to GitHub Pages (Pages build source: GitHub Actions). `static/CNAME` is copied into `dist/` and sets the custom domain `appliance.christiejustice.com`.

DNS: christiejustice.com is hosted at WordPress.com nameservers (ns1/ns2/ns3.wordpress.com). A record is required: `CNAME  appliance  ->  christiemogulreport.github.io` (same pattern as `shred`). After it resolves, enable "Enforce HTTPS" in the repo's Pages settings.

Commit identity: `Black Swan Sibyl <noreply@users.noreply.github.com>`.

`data/` and `tools/` are gitignored (private idea backlog and outreach notes).
