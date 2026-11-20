# Tools — PriceDrop Hunter

A single self-contained page listing all ten PriceDrop Hunter tools in one
place, served at `http://satyamraj.in/tools`. No build step: all CSS and JS
are inline in `index.html`. The one external dependency is Google Fonts
(Plus Jakarta Sans for headings, Inter for body, loaded from
`fonts.googleapis.com` with system-font fallbacks if it fails to load).

## The page

Light, colourful design — a bold redesign, deliberately different from
the hub: warm off-white page, oversized headline ("Every tool. One page.")
with a yellow marker highlight on the second line, a stats strip (10
tools, 9 stores + hub, ₹0 free), a colour strip with one segment per tool,
and white cards with a vibrant per-store accent bar, emoji icon tile and
brand-coloured button. No theme toggle: the page is light by design.
Typography is Plus Jakarta Sans (headings) over Inter (body). The top nav
is slim and sticky ("Tools" wordmark, links to All tools / About / How it
works), cards lift on hover with soft layered shadows, and sections fade in
gently on scroll (disabled under `prefers-reduced-motion`).

Sections, in order:

1. **Hero** — headline, one-line intro, a prominent "Open PriceDrop Hunter"
   button to `http://satyamraj.in/PriceDrop-Hunter/`, and the stats strip
   (true counts only — no invented user counts, ratings or savings).
2. **All tools** — the full grid of all 10 tools, hub first as a featured
   full-width yellow card, with the search box, category filter chips and
   "Showing X of 10 tools" count.
3. **About the Developer** — a proper first-person intro: Satyam Raj,
   Software Developer working on AI projects at Extension Technologies
   (1+ years), founder of Setuware Technologies, B.Tech CSE from DIT
   University, Dehradun (class of 2024), builder of PriceDrop Hunter
   (nine store deal-finders plus a Telegram deals bot sending fresh deals
   every 15 minutes), and open-source contributor (Kestra,
   terraform-aws-github-runner) — plus highlight chips. Uses only
   verified wording (no invented biographical detail, no social/GitHub
   links); the word "Telegram" appears once, in the About prose only.
4. **How to use** — 3 simple steps, plus a short FAQ (free? account?
   which stores?) whose answers are verified against the live tool pages.
5. **Footer** — one line linking back to PriceDrop Hunter.

## Tools

| Tool | Category | Live page |
|---|---|---|
| PriceDrop Hunter — All Stores | All Stores | http://satyamraj.in/PriceDrop-Hunter/ |
| Flipkart Minutes Deals | Shopping | http://satyamraj.in/Flipkart-Minute-Deals/ |
| Blinkit Deals | Grocery & Quick Commerce | http://satyamraj.in/Blinkit-Deals/ |
| Amazon Now Deals | Shopping | http://satyamraj.in/Amazon-Now-Deals/ |
| Swiggy Instamart Deals | Grocery & Quick Commerce | http://satyamraj.in/Swiggy-Instamart-Deals/ |
| BigBasket Deals | Grocery & Quick Commerce | http://satyamraj.in/BigBasket-Deals/ |
| Zepto Deals | Grocery & Quick Commerce | http://satyamraj.in/Zepto-Deals/ |
| JioMart Deals | Grocery & Quick Commerce | http://satyamraj.in/JioMart-Deals/ |
| Myntra Deals | Fashion | http://satyamraj.in/Myntra-Deals/ |
| Croma Deals | Electronics | http://satyamraj.in/Croma-Deals/ |

All links use `http://` — HTTPS does not serve on this domain yet.

## How to add a new tool card

Edit the cards block in `index.html` (between the `<!-- CARDS -->` and
`<!-- /CARDS -->` markers) and copy an existing `<article class="store">`
card, keeping the hub order (hub card first, featured, then the stores).
For the new card, set:

- `data-name` — the tool's bookmark name (this is what search matches).
- `data-category` — one of the existing categories: `Grocery & Quick Commerce`,
  `Shopping`, `Fashion`, `Electronics`, `All Stores`. If the tool needs a new
  category, add a matching chip button in the `#chips` group as well.
- `.top` band `background` — the tool's brand colour; the icon chip `<i>`
  gets a contrasting brand colour.
- The tag, one-line description, and two bullet facts, matching the wording
  on the hub and the tool's own page.
- The single button: class `sb fill`, `style="background:<brand colour>"`,
  label `Open tool →`, `aria-label="Open <Tool Name>"`, linking to the tool's
  live page at `http://satyamraj.in/<Repo>/`.

Keep the page self-contained apart from the Google Fonts link: no other
external fonts, scripts, images, or links outside the live tool pages and
the hub link in the header and footer.
