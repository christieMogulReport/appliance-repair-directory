# Appliance Repair Help

Static directory site (Python + Markdown) for washer, dryer, refrigerator, and dishwasher repair help. Brand: Black Swan Sibyl (Christie Justice). Timezone: America/Chicago.

**Intended domain:** something like `appliance.christiejustice.com`. This is **unconfigured**: there is no `static/CNAME`, no GitHub repo, and nothing is deployed. `base_url` in `config.yml` is a placeholder until the domain is set up.

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

## Deploy (not done yet)
`.github/workflows/pages.yml` is included for GitHub Pages, but no repo exists and nothing has been pushed. When a domain is chosen, add `static/CNAME` and update `base_url`.

`data/` and `tools/` are gitignored (private idea backlog and outreach notes).
