# HORA Abeshu Lab Website

Local Jekyll/GitHub Pages-ready website for the HORA Abeshu Lab at New Mexico State University.

This site is intentionally simple: Markdown pages, YAML data files, small Liquid layouts, and local SVG placeholder graphics. Deployment is not enabled yet.

## Running locally

Install Ruby and Bundler if they are not already available, then run:

```bash
bundle install --path vendor/bundle
bundle exec jekyll serve
```

Open the local preview URL printed by Jekyll, usually:

```text
http://127.0.0.1:4000/
```

## Previewing in VS Code

This repository includes VS Code tasks for local preview.

1. Open the repository folder in VS Code.
2. Run `Terminal > Run Task... > Jekyll: serve site`.
3. Open the command palette and run `Simple Browser: Show`.
4. Enter:

```text
http://127.0.0.1:4001/
```

Useful preview URLs:

```text
http://127.0.0.1:4001/updates/
http://127.0.0.1:4001/manual/
```

To build without serving:

```bash
bundle exec jekyll build
```

The generated site will be placed in `_site/`, which is ignored by git.

## Editing pages

Main pages live at the repository root:

- `index.md`
- `research.md`
- `people.md`
- `publications.md`
- `software-data.md`
- `opportunities.md`
- `updates.md`
- `team-resources.md`
- `contact.md`

Each page has YAML front matter at the top. Edit the Markdown or HTML/Liquid content below the front matter.

## Editing site information

Global lab information is in `_config.yml` under the `lab:` key. Update this file for institution, department, PI name, email, and site metadata.

Navigation links are in `_data/navigation.yml`.

Before public deployment, set the final production URL in `_config.yml`:

```yaml
url: "https://example.edu"
baseurl: ""
```

The canonical links, Open Graph image URLs, `robots.txt`, and `sitemap.xml` depend on the final URL.

## Editing the lab manual

The lab manual lives under:

```text
manual/
```

Manual navigation is controlled by:

```text
_data/manual_navigation.yml
```

Manual pages use the `manual` layout, which provides a dedicated manual sidebar while keeping the public site header and footer.

Starter manual pages include onboarding, graduate studies, research workflows, programming, writing and reviewing, HORA software, other software, data visualization, job search, templates, and resources.

## Adding updates

Update posts live in `_posts/`.

Create a new file using this naming pattern:

```text
YYYY-MM-DD-short-title.md
```

Use this front matter:

```yaml
---
layout: post
title: Example update title
date: YYYY-MM-DD
category: updates
---
```

Then write the post body in Markdown.

## Adding people

People data lives in `_data/people.yml`.

The current PI profile is already defined there. Add students, undergraduate researchers, and alumni when real names and details are ready. Do not add placeholder people as real entries.

The PI image path can be set when an approved headshot is available:

```text
assets/img/pi-placeholder.svg
```

Use an approved headshot or another image you have rights to use. Leave the image field blank to render the profile without a placeholder.

## Adding publications

Publication placeholders live in `_data/publications.yml`.

Add real entries only when ready. Example:

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

The publications page automatically renders entries from this file.

## Design edits

Site styling is in:

```text
assets/css/style.css
```

The current palette uses NMSU-inspired crimson/maroon, dark navy, white/light gray, and blue/teal accents.

## Image credits

- `assets/img/nmsu-campus-panorama.jpg`: Panoramic view of New Mexico State University from Tortugas ("A") Mountain by Terry Umbenhaur, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:NMSU_Campus.jpg), licensed under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).
- `assets/img/nmsu_view.webp`: Campus aerial view used for NMSU location and contact sections.
- `assets/img/hora-hero.png`: Generated local hero image for the HORA Abeshu Lab website.
- `assets/img/pi-placeholder.svg`: Local placeholder SVG.
- `assets/img/nm-rio-grande-bosque.jpg`: Rio Grande River and bosque near Albuquerque, New Mexico by Asaavedra32, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Rio_Grande_River_and_Bosque.JPG), licensed under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). Resized for web use.
- `assets/img/nm-rio-grande-gorge.jpg`: Rio Grande Gorge near Taos, New Mexico by Tobyw87, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:RioGrandGorge.jpg), licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-organ-mountains.jpg`: View of the Organ Mountains outside Las Cruces, New Mexico by SteveStrummer, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Organ_Mountains_Las_Cruces_NM.JPG), dedicated to the public domain under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Resized for web use.
- `assets/img/nm-elephant-butte.jpg`: Elephant Butte Lake, New Mexico by Kfasimpaur, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Elephant_butte_lake-kmf.JPG), released to the public domain. Resized for web use.
- `assets/img/nm-white-sands.jpg`: Dunes in White Sands National Park by Krzysztof Ziarnek, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:White_Sands_NP_kz02.jpg), licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Resized for web use.
- `assets/img/nm-valles-caldera.jpg`: Panorama of Valles Caldera, New Mexico by Thomas Shahan, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Panorama_of_Valles_Caldera,_New_Mexico_(7271433464).jpg), licensed under [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/). Resized for web use.

## Future deployment

Deployment is not enabled yet.

This repository does not include a GitHub Actions deployment workflow, and GitHub Pages has not been enabled. Do not publish until the site has been reviewed.

When ready, a future deployment path could be:

1. Push this repository to GitHub.
2. In the GitHub repository settings, enable GitHub Pages.
3. Select the branch and folder to publish, commonly `main` and `/root`.
4. Confirm the generated Pages URL.
5. Optionally add a custom domain after reviewing DNS and HTTPS settings.

If a GitHub Actions deployment workflow is preferred later, add it only after review.
