---
layout: manual
title: How to Edit This Manual
summary: How to update the HORA lab manual without breaking the public website.
---

## Where the Manual Lives

The manual lives in the `manual/` folder of the website repository. Each page is a Markdown file with front matter at the top.

Example:

```markdown
---
layout: manual
title: Page Title
summary: One sentence summary.
---

## First Heading

Page content goes here.
```

## Adding a New Manual Page

1. Create a new Markdown file under `manual/`.
2. Use `layout: manual` in the front matter.
3. Add the page to `_data/manual_navigation.yml`.
4. Build the site locally before publishing.

## Local Preview

Use the VS Code task:

```text
Terminal > Run Task... > Jekyll: serve site
```

Then preview:

```text
http://127.0.0.1:4001/manual/
```

## Writing Style

- Write for a future lab member who needs to act.
- Keep pages specific and maintainable.
- Prefer checklists, examples, and links over long essays.
- Avoid storing passwords, private data, unpublished sensitive results, or confidential collaborator information.
- Include dates or version notes when guidance may become outdated.
