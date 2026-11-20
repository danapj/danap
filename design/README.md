# Design system

The visual and writing rules for danapek.com. The browsable version, with live component examples, is the "Dana Pek" design system in Claude (https://claude.ai/artifact/RCvE93f6RtZn1MvmohwEs3).

- `tokens.json`: every colour, text style, spacing step and layout value, with a note on when to use it.
- `tokens.css`: the same values as CSS variables, matching the `:root` block in `preview/index.html`.

When you change a value, change it here and in the site’s `:root` block so they stay in step.


A quiet, text-first system for a portfolio about language systems. Serif for reading, sans for small details, thin rules instead of boxes. Built from the live site at danapek.com.

## Principles

- **The writing does the work.** One reading column, no cards, no decoration. If something needs emphasis, the words carry it first.
- **Six sizes, no others.** Every piece of text uses one of the type styles below. If a new element seems to need a new size, it's a sign the hierarchy is wrong.
- **Rules, not boxes.** Content is grouped by 1px `line` rules between rows. Nothing has a background fill, a shadow or a rounded corner.
- **Serif reads, sans labels.** Anything meant to be read is set in Lora. Inter appears only small and in `muted` or `body`: dates, tags, captions, navigation, footer.
- **One accent, used rarely.** `highlight` marks a few words at most, like a pen on paper.

## Voice and content

Friendly, warm and plain, like talking to a colleague you like. The examples come from the site.

- Say hello. Pages open like a person would: "Hi! I’m Dana." Calls to action are invitations: "Say hi", "Happy to walk you through any of them over a call."
- First person, everyday verbs. "I design content", "got our localization off the ground", not "spearheaded" or "language infrastructure".
- Describe work by what it did for people. "Helped make it easier for travellers to book trips", "simplified investing", "improved access to maths education".
- A little personality is welcome: "In a past life…", "turned out surprisingly useful", "what’s bugging you". One light touch per paragraph, not a joke in every line.
- Short sentences. Lead with the outcome, then the detail.
- Sentence case everywhere, including headings and links.
- No em dashes, no "not X, but Y", no stock phrases. Say the thing once.
- Numbers as numerals, with the unit: "16+ languages", "20+ studies", "days to minutes".
- Project titles describe what was made: "A terminology system built for people and AI", not "Project Glossary".
- Meta lines follow one pattern: `Company, year · Category`.

## Colour

| Token | Use for | Contrast on paper |
| --- | --- | --- |
| `paper` | The page. The only surface. | — |
| `ink` | Name, headings, titles, lead paragraphs, prose | 16.4:1 |
| `body` | Descriptions, lists, table values, footer | 8.4:1 |
| `muted` | Dates, tags, captions, labels, inactive nav | 4.75:1 |
| `line` | 1px rules and image frames. Never text. | decorative |
| `highlight` | A marker behind a few words | ink on it 15.3:1 |
| `white` | Behind screenshots | — |

Text hierarchy comes from colour as much as size: `ink` for what you read first, `body` for what supports it, `muted` for details you scan.

## Type

Two families from Google Fonts: **Lora** (400, 500, 600, italic 400 and 600) and **Inter** (400).

| Style | Size / line | Font | Use |
| --- | --- | --- | --- |
| `display` | 46 / 1.1, italic 600 | Lora | The name, once per page |
| `lead` | 26 / 1.4 | Lora | Opening paragraph of every page, in `ink` |
| `heading` | 26 / 1.3, italic | Lora | Section headings |
| `title` | 21 / 1.3, 500 | Lora | Row titles |
| `body` | 18 / 1.6 | Lora | All reading text |
| `ui` | 15 / 1.5 | Inter | Nav, filters, footer |
| `meta` | 14 / 1.5 | Inter | Dates, tags, captions, labels |

`lead` and `heading` share a size on purpose: the lead is upright and opens a page; a heading is italic and opens a section, with `space-8` above it. On phones `display`, `lead`, `heading` and `title` step down (38, 22, 22, 19). Body text never goes below 18px.

Bold appears only as a short lead-in inside a sentence ("**The call I made:**"), in Lora 600.

## Spacing and layout

- One column, `measure` 720px wide, at least `gutter` 20px from the screen edge.
- Rows have `space-5` (20px) above and below, with a `line` rule between.
- Section headings have `space-8` (64px) above and `space-4` (16px) below.
- Paragraphs are separated by one line of their own size (1em).
- Images sit inside a 1px `line` frame on `white`, with a `meta` caption `space-2` below.

## Components

| Component | What it's for |
| --- | --- |
| Row | The core unit: title, meta line, description. Used for projects, packages and list items. |
| ExpandableRow | A Row that opens to show points, a call-out and an image. |
| LabelValue | Two-column facts: a `meta` label beside a `body` value. |
| Steps | A numbered sequence, one step per row. |
| Filter | Text links that filter a list of rows by category. |
| Nav | The page links under the name. |
| Primary link | The one call to action: "Work together →" in the nav and "Say hi to get started →". `ui` size, weight 500, `ink`, with an arrow. Never a filled button. At most one per screen. |

## Imagery

No logo: the name set in `display` is the mark. No icons apart from the + / − toggle, which is drawn with two 1.5px strokes in a `radius-round` circle with a `line` border. Photos are cropped 4:5 in a grid of three (two on phones). Screenshots keep their own proportions and get the 1px frame.

## Don't

- Add a size, weight or colour that isn't in this system.
- Use uppercase letter-spaced labels. Use a `heading` or a `meta` line instead.
- Put content in cards, tinted boxes or anything with a shadow or radius.
- Use `muted` for anything longer than a line, or `line` for text.
- Use `highlight` as a background for blocks, buttons or more than a few words.
- Make a call to action a filled or outlined button. Use the primary link instead.

## Using it in code

```css
:root{
  --paper:#f8f8f6; --ink:#1a1a19; --body:#4a4a45; --muted:#6f6f69; --line:#dcdcd6; --highlight:#fff1a8;
  --serif:"Lora", Georgia, serif; --sans:"Inter", system-ui, sans-serif;
  --t-display: italic 600 clamp(38px,5vw,46px)/1.1 var(--serif);
  --t-lead:    400 clamp(22px,2.6vw,26px)/1.4 var(--serif);
  --t-heading: italic 400 clamp(22px,2.6vw,26px)/1.3 var(--serif);
  --t-title:   500 clamp(19px,2vw,21px)/1.3 var(--serif);
  --t-body:    400 18px/1.6 var(--serif);
  --t-ui:      400 15px/1.5 var(--sans);
  --t-meta:    400 14px/1.5 var(--sans);
}
```

Load the fonts with `https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,600&family=Inter:wght@400;500&display=swap`.
