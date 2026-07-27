
<p align="center">
  <img src="assets/img/hil-logo.png" alt="Abeshu Hydrosystems Intelligence Lab logo" width="1000">
</p>


# Website for Abeshu Lab at [New Mexico State University](https://ce.nmsu.edu/)

[![Site check](https://github.com/Hydrosystems-Intelligence-Lab/hydrosystems-intelligence-lab.github.io/actions/workflows/site-check.yml/badge.svg)](https://github.com/Hydrosystems-Intelligence-Lab/hydrosystems-intelligence-lab.github.io/actions/workflows/site-check.yml)
![Jekyll](https://img.shields.io/badge/Built%20with-Jekyll-cc0000)
![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-222222)
![Website](https://img.shields.io/website?url=https%3A%2F%2Fhydrosystems-intelligence-lab.github.io%2F)

The site is a Jekyll project: Markdown pages, YAML data files, and Liquid layouts.

## Repository structure

Main pages live at the repository root: `index.md`, `research.md`, `people.md`, `publications.md`, `software-data.md`, `opportunities.md`, and `updates.md`. Each has YAML front matter at the top with the Markdown body below. The lab handbook lives at `/manual/`.

Site metadata (institution, department, PI, email, URL) is in `_config.yml` under the `lab:` key. Top-level navigation is in `_data/navigation.yml`. Site styling is in `assets/css/style.css`, using an NMSU-inspired palette of crimson/maroon, dark navy, white/light gray, and blue/teal accents.

The research lab handbook lives in `manual/` and uses the `manual` layout, which provides a dedicated sidebar while keeping the public site header and footer. Handbook navigation is in `_data/manual_navigation.yml`. Sections cover onboarding, graduate studies, research workflows, programming, writing and reviewing, lab software, other software, data visualization, job search, templates, and resources.

## Adding content

**Updates.** Create a file in `_posts/` named `YYYY-MM-DD-short-title.md`:

```yaml
---
layout: post
title: Example update title
date: YYYY-MM-DD
category: updates
---
```

**Team.** Edit `_data/people.yml`. The PI profile is defined; add students, undergraduate researchers, and alumni as real details become available. For headshots, set the image path to an approved photo, or leave the field blank to render without one.

**Publications.** Edit `_data/publications.yml`. The publications page renders entries automatically:

```yaml
journal_articles:
  title: Journal Articles
  items:
    - title: "Paper title"
      authors: "Author A, Author B"
      venue: "Journal Name"
      year: 2027
      url: "https://doi.org/example"
```

## Image credits

- `assets/img/nmsu-campus-panorama.jpg`: Panoramic view of NMSU from Tortugas ("A") Mountain by Terry Umbenhaur, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:NMSU_Campus.jpg), [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).
- `assets/img/water-systems-hero.png` (and the `water-systems-hero-{960,1600}.{jpg,webp}` renditions built from it): AI-generated composite produced locally for this website. Used as the homepage hero. Not a photograph and not a depiction of a specific real site.
- `assets/img/research-*.png` (and the `-760.{jpg,webp}` renditions): AI-generated illustrations produced locally for this website. Illustrative only — they do not present research results or real data.
- `assets/img/hil-logo.png`, `hil-emblem.png`, `hil-logo-labeled.png` (and the `hil-logo-600.{jpg,webp}` renditions): lab logo artwork produced for the Abeshu Hydrosystems Intelligence Lab.
- `assets/img/pi-guta.JPG` (and `pi-guta-480.{jpg,webp}`): photograph of the PI, supplied by the PI.
- `assets/img/pi-placeholder.svg`: Local placeholder SVG.
- `assets/img/nm-rio-grande-gorge.jpg`: Rio Grande Gorge near Taos by Tobyw87, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:RioGrandGorge.jpg), [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-organ-mountains.jpg`: Organ Mountains outside Las Cruces by SteveStrummer, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Organ_Mountains_Las_Cruces_NM.JPG), [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Resized for web use.
- `assets/img/nm-elephant-butte.jpg`: Elephant Butte Lake by Kfasimpaur, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Elephant_butte_lake-kmf.JPG), public domain. Resized for web use.
- `assets/img/nm-white-sands.jpg`: White Sands National Park by Krzysztof Ziarnek, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:White_Sands_NP_kz02.jpg), [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-valles-caldera.jpg`: Valles Caldera panorama by Thomas Shahan, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Panorama_of_Valles_Caldera,_New_Mexico_(7271433464).jpg), [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/). Resized for web use.

### Unresolved provenance — do not publish these until confirmed

- `assets/img/nmsu-campus-gateway.jpg`: **Provenance unknown.** This file was previously named
  `nm-rio-grande-bosque.jpg` and credited above as a Wikimedia CC BY-SA photo of the Rio Grande bosque.
  It is not that image — it is a twilight photograph of the NMSU campus entrance gateway, most likely an
  NMSU marketing photograph. The incorrect credit has been removed and the file renamed to match its
  actual content. **It is currently unreferenced by the site.** Confirm the source and licence before
  using it, or delete it.
- `assets/img/background_image_nmsu.jpg`: **Provenance undocumented.** Used as the `.home-intro-section`
  background in `assets/css/style.css`. Appears to be an Organ Mountains/campus sunset photograph.
  Source, photographer, and licence are unknown. Confirm before launch.

## Previewing changes

Before publishing changes, preview the website locally from the repository root
(the Jekyll project lives at the root of this repo).

Install dependencies once:

```sh
gem install bundler jekyll
bundle install
```

Then start the local preview server:

```sh
bundle exec jekyll server
```

Open the site at:

```text
http://localhost:4000/
```

This repo is named `<org>.github.io`, so `baseurl` in `_config.yml` is empty
(`""`) and the site is served at the root, both locally and once deployed at
<https://hydrosystems-intelligence-lab.github.io>.

Useful flags:

- `bundle exec jekyll server --future` — also render future-dated posts (the
  posts in `_posts/` are dated to the lab launch, so they are hidden by default
  until that date).
- `bundle exec jekyll server --livereload` — auto-refresh the browser on save.

### Troubleshooting

**`bundle exec jekyll server` reports missing gems / `command not found: jekyll`,
even though `vendor/bundle` exists.** Bundler has lost the local install path.
Re-point it (this repo uses Bundler 1.x with system Ruby, so use the 1.x
syntax), then verify:

```sh
bundle config --local path vendor/bundle
bundle check        # should report "The Gemfile's dependencies are satisfied"
```

On Bundler 2.x the equivalent command is `bundle config set --local path vendor/bundle`.
