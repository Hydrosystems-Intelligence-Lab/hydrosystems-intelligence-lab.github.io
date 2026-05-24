
<p align="center">
  <img src="assets/img/AWSI.png" alt="Abeshu Hydrosystems Intelligence Lab logo" width="1000">
</p>

# Abeshu Hydrosystems Intelligence Lab Website

[![Site check](https://github.com/gutabeshu/Hydrosystems-Intelligence-Lab/actions/workflows/site-check.yml/badge.svg)](https://github.com/gutabeshu/Hydrosystems-Intelligence-Lab/actions/workflows/site-check.yml)
![Jekyll](https://img.shields.io/badge/Built%20with-Jekyll-cc0000)
![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-222222)
![Website](https://img.shields.io/website?url=https%3A%2F%2Fgutabeshu.github.io%2FHydrosystems-Intelligence-Lab%2F)

Source for the website of the Abeshu Hydrosystems Intelligence Lab at New Mexico State University.

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
- `assets/img/water-systems-hero.png`: Generated local hero image for the research lab website.
- `assets/img/pi-placeholder.svg`: Local placeholder SVG.
- `assets/img/nm-rio-grande-bosque.jpg`: Rio Grande River and bosque near Albuquerque by Asaavedra32, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Rio_Grande_River_and_Bosque.JPG), [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). Resized for web use.
- `assets/img/nm-rio-grande-gorge.jpg`: Rio Grande Gorge near Taos by Tobyw87, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:RioGrandGorge.jpg), [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-organ-mountains.jpg`: Organ Mountains outside Las Cruces by SteveStrummer, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Organ_Mountains_Las_Cruces_NM.JPG), [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Resized for web use.
- `assets/img/nm-elephant-butte.jpg`: Elephant Butte Lake by Kfasimpaur, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Elephant_butte_lake-kmf.JPG), public domain. Resized for web use.
- `assets/img/nm-white-sands.jpg`: White Sands National Park by Krzysztof Ziarnek, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:White_Sands_NP_kz02.jpg), [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-valles-caldera.jpg`: Valles Caldera panorama by Thomas Shahan, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Panorama_of_Valles_Caldera,_New_Mexico_(7271433464).jpg), [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/). Resized for web use.

## Previewing changes
Before publishing changes, one can preview the website using bundle

```yaml
gem install bundler jekyll
bundle install
bundle exec jekyll serve
```
