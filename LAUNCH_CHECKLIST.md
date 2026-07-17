# Lab Launch Checklist (target: late August 2026)

Everything needed to take the Hydrosystems Intelligence Lab org live. Work top to bottom.
This file is excluded from the Jekyll build (`exclude:` in `_config.yml`) — it never appears on the site.

## Already done (no action needed)

- [x] Org health files (CODE_OF_CONDUCT, CONTRIBUTING, SECURITY, SUPPORT) merged to `main` in the `.github` repo (PR #1, July 2026).
- [x] CODEOWNERS in `hsi-lab-template-code` points to `@gutabeshu`.
- [x] Website: RSS feed, JSON-LD, Research Foundations section, Contact page, Google Scholar link (July 2026).

## Before launch day

- [ ] Create a Cloudflare Web Analytics token (dash.cloudflare.com → Analytics & Logs → Web Analytics), paste it into `_config.yml` → `analytics.cloudflare_token`, commit and push.
- [ ] Optional: replace AI-generated research images in `assets/img/research-*.png` with real figures as they become available.
- [ ] Preview the full site locally: `bundle exec jekyll serve --future` → http://localhost:4000/ (the `--future` flag shows the three posts dated 2026-08-17).

## Launch day (all in the GitHub web UI — gh CLI is not installed locally)

1. [ ] Make all five repos **public**: repo → Settings → General → Danger Zone → Change visibility.
   - `hydrosystems-intelligence-lab.github.io` (required: GitHub Pages on a free org plan only works on public repos)
   - `.github` (required: org profile README and default health files only take effect when public)
   - `hsi-lab-template-code`
   - `hsi-lab-template-presentations`
   - `hsi-lab-curated-research-tools`
2. [ ] Enable GitHub Pages: `hydrosystems-intelligence-lab.github.io` → Settings → Pages → Deploy from a branch → `main` / `/ (root)`.
3. [ ] Enable the template toggle on **both** template repos: Settings → General → ☑ **Template repository**. Without this the green "Use this template" button never appears.
   - `hsi-lab-template-code`
   - `hsi-lab-template-presentations`
4. [ ] If launch happens **before Aug 17**: the three future-dated posts in `_posts/` will not render until a build runs on/after that date. GitHub Pages only rebuilds on push — push any commit on/after Aug 17 (or re-date the posts to the actual launch date).

## Post-launch verification

- [ ] Site loads at https://hydrosystems-intelligence-lab.github.io/ and all nav pages render (Home, Research, Team, Publications, Lab Handbook, Join, Updates, Contact).
- [ ] Updates page shows the three launch posts and https://hydrosystems-intelligence-lab.github.io/feed.xml serves the RSS feed.
- [ ] Lab Handbook pages' links to the org GitHub repos resolve (they 404 if any repo was left private).
- [ ] Org page https://github.com/Hydrosystems-Intelligence-Lab shows the profile README, and both template repos show the "Use this template" button.
- [ ] Cloudflare Analytics dashboard starts receiving page views.
- [ ] Check the site on a phone; run one page through https://validator.schema.org/ to confirm the JSON-LD parses.
