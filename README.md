# azeniq.com

The landing page for azeniq.com, a domain that is for sale. Its one job is to
turn a visitor who typed the name into the address bar into a considered offer.

Live at **https://azeniq.com**

## How it's built

One file. `index.html` holds the markup, styles, and script inline — no build
step, no dependencies, no framework. Deploying means serving that file. Type is
set in the system font stacks, so there are no webfont requests.

```
index.html   the page
CNAME        binds the hosted site to the apex domain
```

## Structure

The page runs in one column, top to bottom:

| Section    | What it does                                                       |
| ---------- | ------------------------------------------------------------------ |
| Hero       | The domain set large in mono, with its spec line                    |
| Ledger     | The page's argument: alternative name shapes and what each costs    |
| Fits       | Sectors the name has been read as, so buyers self-identify          |
| Offer      | The form. No listed price; buyers name a figure                     |
| Process    | Three steps, settled through escrow                                 |
| FAQ        | Transfer mechanics, offer expectations, payment, payment plans      |

The ledger is the part that does the work. Rather than listing the domain's
attributes, it prices the alternatives — `azeniq.io`, `getazeniq.com`, and the
rest — by what each one costs the buyer to keep explaining.

## Editing

Everything is in `index.html`, in document order.

- **Colour and type** — the custom properties in `:root` at the top of the
  `<style>` block. Every value on the page derives from them.
- **Motion** — the hero characters stagger in on load and nothing else animates.
  `prefers-reduced-motion` is respected.
- **Copy** — plain HTML.

## Running it locally

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. Opening the file directly with `file://` works
too, though the offer form needs to be served over http to submit.

## Quality floor

Responsive from 320px up, keyboard-navigable with visible focus states, reduced
motion respected, and text contrast at 4.5:1 or better throughout.
