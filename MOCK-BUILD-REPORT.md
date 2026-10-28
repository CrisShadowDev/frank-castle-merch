# Frank Castle Brand - Mockup Build Report, Updated with Real Art
Date: Oct 28, 2026, America/New_York
Status: MOCKUP ONLY, TEST ONLY. No real sales, no real Stripe, no supplier, no money.

## What changed in this update
- Replaced placeholder-only SVG art with Crishtian's actual uploaded 3x3 grids.
- Split all 9 grids into 81 cells (9 per grid), inset to cut grid lines.
- Created original JPG cells and transparent PNG cells for every cell.
- Updated index/shop to use real cells on tee/sticker/mug mockups.
- Added designs.html with all 9 full grids and all 81 cells.
- GitHub Pages enabled, Vercel project created but NOT Git-linked (403 team-scope, same as prior builds).

## Grids, verified visually
- grid11 (10463): neon chickens, skull buckets, machines, purple/pink/green on black
- grid12 (10467): crown chickens, hooded figures, candles, crosses, purple/pink on black
- grid13 (10466): neon crown chickens, candle buckets, hooded figures, purple/pink/cyan on black
- grid14 (10465): color chickens, skull cauldrons, fire buckets, purple/blue/orange on dark
- grid15 (10464): neon muscle chickens, skull buckets, winged chickens, purple/cyan on black
- grid16 (10468): CLUCK CLUCK MOTHER F! text, purple, red, white, green, gold, yellow, orange, pink on black
- grid17 (10469): CLUCK! CLUCK! text, purple, red, white, gold, pink, green on black
- grid18 (10470): chickens, CLUCK! CLUCK! text, green bucket, and KFC-flagged bucket cell 8
- grid19 (10471): chickens in purple, red, white, gold, green, and KFC-flagged bucket cell 8

## Cells used on products (shop/index)
T-shirts (transparent PNG on black tee mockup):
- grid11 cell 1 - Neon Rooster
- grid12 cell 2 - Crown Chicken
- grid16 cell 2 - CLUCK CLUCK MOTHER F! Red
- grid17 cell 1 - CLUCK! CLUCK! Purple
Stickers (transparent PNG, white border):
- grid19 cell 1 - Purple Chicken
- grid16 cell 5 - CLUCK Green Text
- grid11 cell 4 - Skull Bucket
Mugs (original JPG cell on black mug mockup):
- grid19 cell 5 - Green Bucket
- grid14 cell 5 - Fire Bucket
- grid13 cell 2 - Neon Chicken
Future buckets (not orderable):
- Popcorn Bucket: grid11 cell 4 / grid15 cell 2, supplier not confirmed
- Chicken Bucket: grid19 cell 8 / grid18 cell 8, see trademark flag below

## Background removal method
- Tool: Python Pillow + numpy, local, no external service, no credentials.
- Split: image width/3, height/3, inset 14px (1280px grids) / 12px (1024px grids) to cut purple/grey grid lines.
- Transparency: luminance-based alpha. Alpha = 0 below luminance 18, ramp to 255 at luminance 55, clipped. This drops pure black background while keeping neon outlines.
- Limitation, honest: dark blue/purple interiors and dark skull details can become semi-transparent, because they are close to black. For print, the original JPG on a black tee/mug is safer than the transparent PNG, because black blends. Transparent PNGs are provided as a bonus, not as print-ready finals. A human check per cell is still needed before any live print, and a dedicated background remover may do better on dark interiors.
- Files: images/cells/{grid}-cell{N}.jpg (original) and {grid}-cell{N}-transparent.png, 81 x 2 = 162 files, plus images/grids/{grid}.jpg, 9 files. Full set in workspace, selected set in GitHub Pages deploy.

## Trademark flag - KFC
- grid19 cell 8, row 3 col 2, bucket text includes "KFC" (rendered as CLUCK EN CHOTHER MOTHER KFC!).
- grid18 cell 8, row 3 col 2, same bucket design.
- Do NOT sell either as KFC merch, do NOT use KFC branding, rename to CLUCK Bucket only, or remove the cell, before any live use. In this mockup it is shown as a design only, flagged, not as a product for sale.

## GitHub
- Repo: https://github.com/CrisShadowDev/frank-castle-merch
- Pages URL: https://crisshadowdev.github.io/frank-castle-merch/
- Pages enabled 201, source main / root. Full pages + selected cells + resized grids uploaded, 39 files, all 200/201.
- Full 81-cell set is in ~/workspace/frank-castle-merch/images/cells/, not all in the Pages deploy, to keep the deploy light. Designs page in Pages shows full grids and selected cells; workspace Designs page shows all 81 cells.

## Vercel
- Project: frank-castle-merch, prj_Y9OyqKVaMs5cWr2K2rbuqMLANg3S, team reality-dev-phantom
- File deployment via MCP was blocked by argument-size limit for image-heavy payloads (even a 520KB mini payload exceeded the exec argument limit).
- Git-link attempt: create_git_project returned 403, Not authorized, scope reality-dev-phantom, same limitation as prior builds. Future GitHub pushes will NOT auto-pull to Vercel until team access is granted.
- Viewable preview is therefore GitHub Pages, NOT a Vercel URL. Do NOT claim a Vercel live URL for this update.

## Still needed before any live store
1. Brand name confirmation (Frank Castle Brand, exact spelling, person vs brand)
2. Final product list and real prices (all TBD / PLACEHOLDER now)
3. Human check of transparent PNGs, especially dark interiors, and final print files
4. Supplier choice + permission, especially for popcorn / chicken buckets
5. Rename or remove KFC-flagged cells before any live use
6. Stripe owner choice, with explicit approval, if ever live
7. Domain decision, none bought
8. Crishtian manages site/merch, Frank posts - no income amount claimed, no business details invented

## Oct 28 update — line tabs, phone tap preview, subtle neon glow
- KFC: Crishtian does NOT own a KFC yet. A franchise one day is a dream only, not ownership, not a claim. KFC cells grid18 cell 8 / grid19 cell 8 remain flagged, renamed in shop as Future Only / Trademark Flagged, do NOT sell as KFC merch.
- Line tabs added: All lines / T-Shirts / Stickers / Coffee Mugs / Future Buckets / All Designs. On Shop they filter in place (and shop.html#line-tees etc. pre-filters); on Home/Designs/About/Contact they link to the Shop line. No products, cells, or prices changed — all prices remain TBD / PLACEHOLDER.
- Floating preview: phone-first. Tap a main card, or its 'Tap to preview larger' button, opens a full-screen floating preview with the design larger, Close button, tap-outside to close, Escape to close. This works on phone because it is tap/click, not hover-only. Desktop hover also shows a small floating enlarged view near the cursor (fine-pointer only); hover is disabled as the only path on touch devices.
- Neon glow: subtle only — low-opacity radial gradients behind the page, a soft glow box around the hero (box-shadow ~18-28px, pink/cyan at 0.14-0.22 opacity), and soft card glow. Not blinding, no animation.
- Not feasible / not claimed: true mouse hover cannot work on a phone (no cursor), so phone uses tap-to-preview instead — same larger view, different trigger. No Vercel live URL, no Pages live claim. Workspace files are the viewable version.
- Files changed: style.css, app.js, index.html, shop.html, designs.html, about.html, contact.html. No sales, no Stripe, no supplier, no KFC branding added.

## Dark mute sample - approved direction Oct 28, 2026 17:26 ET
- 4 cells desaturated to muted grey/black, neon stripped, from Crishtian's own cells only, no new art generated: grid11-cell1, grid12-cell2, grid11-cell4, grid15-cell2 in images/dark-mute/, preview dark-preview.html.
- Crishtian: "The styles perfect" Oct 28 17:26 ET.
- NOT yet rebuilt: full shop rebuild in dark mute, and GitHub Pages push, are still pending his go. Live Pages is still neon until that rebuild/push is approved and verified.

## Dark muted rebuild - Oct 28, 2026, pushed to Pages
- Full shop rebuilt in dark muted style, approved by Crishtian Oct 28 17:26 ET, rebuild approved 17:27 ET.
- All 81 cells desaturated to grey/black, neon stripped, in images/dark-mute/: 81 dark JPGs, 81 dark transparent PNGs, plus 9 dark grid JPGs. The 4 approved sample JPGs were kept as-is.
- Pages updated: index.html, shop.html, designs.html, about.html, contact.html, style.css (muted grey/black, neon glow removed, line tabs and tap-to-preview kept), dark-preview.html.
- Still mockup only: no real sales, no Stripe, no supplier, prices TBD, KFC-flagged cells grid18/grid19 cell 8 must not be sold as KFC merch, brand name still to confirm.

## Identity clarification Oct 28, 2026 17:33 ET
- Frank Castle is dad's alias only, actual name Bret. Not a separate store owner, not Damon.
- Dad / Frank likes the newer dark muted shop a lot better than the neon version.
- Brand name / person-vs-brand use still to be double-checked and verified with dad when he gets up later. Do NOT rename the store to Bret, and do NOT message dad / Frank about the store, until Crishtian confirms after that check.
