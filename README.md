# figabl-site

Static marketing site. Source lives in `src/`, the deployable page is built to `dist/`.

## Build

```
node build.mjs      # -> dist/index.html + dist/fonts/
```

No dependencies. Node 18+.

## Where to change what

| I want to change...        | Edit this                                  |
|----------------------------|--------------------------------------------|
| Any copy / wording         | `src/sections/<section>.html`               |
| Colours, brand palette     | `src/styles/tokens.css`  (14 CSS variables) |
| Buttons, type scale, grid  | `src/styles/base.css`                       |
| One section's layout       | `src/sections/<section>.css`                |
| Mobile behaviour           | `src/styles/responsive.css`                 |
| Page title, meta, schema   | `src/meta.json`                             |
| Section order / add-remove | `src/sections/manifest.json`                |

Sections, in page order: nav, hero, problem, statement, solution, ethos, steps,
benefits, terracotta, results, team, contact, footer.

Each section is an `.html` + `.css` pair with the same name. They are concatenated
in `manifest.json` order — reordering the page = reordering that array.

## Deploy

`dist/` is a plain static folder. Any static host works. Connect the repo, set:

- build command: `node build.mjs`
- publish directory: `dist`

Pushes to `main` deploy.

## Known gaps

1. **The contact form goes nowhere.** `src/sections/contact.html` has a `<form>`
   with no `action`. Wire it to a form backend before launch.
2. **No mobile nav.** `responsive.css` sets `.nav-links{display:none}` below
   1020px with no replacement — on phones the nav is empty. Needs a menu.
3. **One breakpoint only** (1020px). Nothing between phone and desktop.
4. **`og.png` doesn't exist yet.** Referenced by `src/meta.json`; add a
   1200x630 image at `dist/og.png` or the link previews will be blank.
