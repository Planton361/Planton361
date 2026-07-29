# Version 1 — dark album layout

## Upload structure

Copy the contents of this directory into:

```text
Planton361/Planton361
```

Required structure:

```text
README.md
assets/
├── welcome-dark.gif
├── divider.png
├── photo-album/
│   ├── fraud-prioritization.png
│   ├── life-os.png
│   ├── fh-agent.png
│   └── firered-randomizer.png
└── sections/
    ├── photo-album.png
    ├── now.png
    ├── recent-notes.png
    ├── toolbox.png
    └── sketchbook.png
```

## Header

The animated header:

- is designed for GitHub dark mode;
- shows `WELCOME TO MY SPACE.` for approximately 20 seconds;
- changes to `You have been here as long as you can remember.`;
- holds the second sentence at the end;
- is intentionally minimal and dark.

## Featured projects

Each project uses a wide image-and-text table:

- the photograph receives 58% of the row width;
- the text receives 42%;
- left/right alignment alternates;
- additional technical context stays inside a collapsed photo-back section.

GitHub cannot use custom responsive CSS in a profile README. On narrow screens,
the table remains side by side and becomes smaller. If mobile readability later
becomes more important than desktop presentation, use full-width photographs
with text below instead.

## Private project warning

The four featured repositories are currently private.

Before publishing:

1. review every description;
2. keep `Repository: Private`, or replace it only when a repository becomes public;
3. do not add inaccessible private links;
4. verify that no private implementation detail is exposed.

## Recent Notes

Version 1 uses manually curated notes between:

```html
<!-- RECENT-NOTES:START -->
<!-- RECENT-NOTES:END -->
```

A later GitHub Action can update only this block.

## Planned future work

- automatic Recent Notes;
- structured focus data for the `Now` section;
- an Activity Constellation generated as a custom SVG;
- optional mobile-first album layout.
