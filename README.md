# Tools — PriceDrop Hunter

A single self-contained page listing all ten PriceDrop Hunter tools in one
place, served at `http://satyamraj.in/tools`. No build step, no external
dependencies: all CSS and JS are inline in `index.html`.

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

Keep the page self-contained: no external fonts, scripts, images, or links
outside the live tool pages and the hub link in the header and footer.
