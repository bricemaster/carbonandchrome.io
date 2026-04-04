# Carbon & Chrome Holdings LLC — Landing Page Review

**Reviewed:** 2026-03-27
**File:** `projects/company-site/index.html`
**Screenshots reviewed:** desktop_fold, desktop_full, mobile_fold, mobile_full
**Reference comp:** `archive/streetwear-comp/cc-final.html`

---

## Critic 1 — Visual Design

**Score: 8/10**

### What's Good
- The hero is genuinely impressive. The three-column layout (vertical label | headline | manifesto panel) with the ghost-stroke "build things." text reads as high-end editorial, not startup landing page.
- Typography hierarchy is clear and well-executed: Cormorant Garamond at clamp(62px, 6.5vw, 110px) for the hero, IBM Plex Mono at 7-9px for all labels/overlines, Montserrat for body. Three fonts, three roles, no confusion.
- Gold usage is restrained. It appears only on: overline text, manifesto numbers, bar-val emphasis, section labels, and the CTA button border. Estimated at 5-7% of visible elements — well under the 10% threshold.
- The grain overlay at 2.8% opacity is subtle and adds texture without performance concern.
- The vertical gold rule (left side, gradient-faded) is a premium detail that most sites skip.
- Division cards with watermark numbers (`data-num` pseudo-element at 4% white opacity) and gold bottom-line hover reveal are polished.

### What's Wrong
- **The philosophy section ghost text ("Build") is barely visible at 1.3% opacity.** On the desktop full screenshot it reads as a vague smudge rather than an intentional design element. Either make it 2.5-3% so it's recognizable as text, or remove it.
- **The middle sections (Divisions, Philosophy) feel visually flat on desktop_full.** There is a very large expanse of near-identical dark backgrounds between the hero bar and the footer. The marquee helps break it up, but the Divisions and Philosophy sections both sit on nearly the same shade of dark without enough visual differentiation.
- **The Shop Space CTA radial glow (gold at 6% opacity) is almost invisible.** It should either be stronger (10-12% opacity) to create a real focal point, or removed. Currently it adds rendering cost for no visible payoff.
- **No hero image, illustration, or abstract visual anywhere on the page.** This is a philosophical choice and could be intentional, but 1330 lines of dark text on dark backgrounds risks feeling like a wireframe rather than a finished site. At minimum, the division cards' `.obj-art` zone (referenced in cc-final.html but absent here) should have something.

### Specific Fixes
1. Increase `.philosophy::before` opacity from `0.013` to `0.03`
2. Increase `.shopspace::before` radial gradient gold from `0.06` to `0.12`
3. Add a subtle background shade difference between Divisions (`--void`) and the sections above/below it — even a 2-3 hex step helps

---

## Critic 2 — Brand Consistency

**Score: 7/10**

### What's Good
- Same three-font system as cc-final.html: Cormorant Garamond, Montserrat, and a monospace.
- Same scroll-reveal system (IntersectionObserver, same cubic-bezier, same 28px translateY).
- Same hero layout concept (3-column with manifesto panel, overline + headline + divider + sub).
- Same mono-overline-before-section-title pattern used throughout.
- Same gold-on-void color philosophy. Same grain overlay technique.
- Footer structure matches: 4-column with brand column wider, mono labels, dim link colors.

### What's Wrong
- **Gold color mismatch.** This file uses `--gold: #F0B429` (bright, saturated yellow-gold). The cc-final.html reference and the CC Themes storefront both use `--gold: #b8965a` (muted, warm antique gold). This is the single biggest brand inconsistency. The `#F0B429` reads as "tech startup highlight yellow" not "luxury holding company gold."
- **Mono font mismatch.** This file uses `IBM Plex Mono`. The cc-final.html reference uses `Courier Prime`. The storefront uses `Courier Prime`. IBM Plex Mono is a good font, but it's a different personality — more clinical/tech, less editorial.
- **Background base color mismatch.** `--void: #0D0D0F` here vs `--void: #060606` in cc-final.html. The difference is 7 hex steps brighter. On the screenshots, this makes the company site look slightly lighter/grayer than the storefront's true-black.
- **Ghost-line stroke weight differs.** Company site uses `1.5px` stroke at `0.25` opacity; cc-final uses `1px` at `0.15`. The company site ghost text is noticeably heavier.
- **The hero-sub color differs.** Company site: `var(--silver)` (#AEAEB2). cc-final: `var(--dim)` (#606060). The company site sub-text is significantly brighter, reducing the hierarchy contrast between heading and supporting text.

### Specific Fixes
1. Change `--gold: #F0B429` to `--gold: #b8965a` and `--gold-hi: #FFD060` to `--gold-hi: #d4aa6a`
2. Replace `IBM Plex Mono` with `Courier Prime` in the font import and `--mono` variable
3. Change `--void: #0D0D0F` to `--void: #060606` (and adjust `--deep`, `--carbon`, `--plate` down proportionally)
4. Change `.hero-h1 .ghost-line` stroke to `1px` at `rgba(239,239,239,0.15)` to match cc-final

---

## Critic 3 — Audience Fit

**Score: 9/10**

### What's Good
- The language is excellent for the target audience. "Build people who build things" is a phrase a tradesman puts on his shop wall. It's not clever — it's true.
- "No Gimmicks," "Tools Over Toys," "Quiet Wealth," "Legacy Thinking" — these are value statements that a 35-year-old contractor or auto shop owner would nod at, not roll their eyes.
- "The tradesman who reads. The engineer who creates." — this line specifically validates the audience without patronizing them.
- "Ghost Billionaire" is aspirational without being cringe. It says: you don't need to show off.
- The Shop Space CTA ("Premium websites for trades businesses. Built by a tradesman.") is direct and credentialed. No fluff.
- "Apple x Patagonia x Snap-On x Porsche Culture" — every one of these brands resonates with the target demographic. Snap-On especially signals that this company understands skilled trades.
- The language avoids buzzwords. No "disrupt," no "synergy," no "ecosystem" (wait — "The Ecosystem" is used as a section label). No "leverage," no "scale."
- Division names (Carbon = tools, Chrome = apparel, Campus = experiences) are concrete and masculine without being aggressive.

### What's Wrong
- **"The Ecosystem" as a section label (line 1147) is the one piece of tech-bro language that slipped through.** A tradesman doesn't think in "ecosystems." Consider "The Four Divisions" or just "Divisions."
- **The comparison statement "Apple x Patagonia x Snap-On x Porsche Culture" is bold but risks reading as aspirational-delusional for a company with zero shipped products.** It's the one line where the audience might think "slow down." Consider framing it as a target rather than a claim: "Where Snap-On precision meets Patagonia durability" or similar.
- **No mention of faith/values anywhere.** The CLAUDE.md notes "Christian leaders" as part of the target audience. The site doesn't need to be explicitly religious, but terms like "stewardship," "discipline," "integrity" would resonate and are absent.

### Specific Fixes
1. Change "The Ecosystem" section label to "The Divisions" or "Four Divisions"
2. Soften the brand comparison or reframe as a philosophy rather than a self-comparison
3. Work "stewardship" or "discipline" into the philosophy principles

---

## Critic 4 — Mobile (375px)

**Score: 7/10**

### What's Good
- Nav collapses correctly: center text hidden at 900px, padding reduces at 374px.
- Hero headline scales well via `clamp(42px, 10vw, 62px)` at 480px breakpoint.
- Division cards stack to single column at 480px.
- Footer goes single-column at 480px.
- Touch targets: the `@media (hover: none) and (pointer: coarse)` block sets `min-height: 44px` on all interactive elements. This is correct.
- CTA buttons stack vertically at 480px (`.ss-ctas { flex-direction: column }`).
- `overflow-x: hidden` on body prevents horizontal scroll.

### What's Wrong
- **The hero manifesto panel items at 375px have very tight text.** The manifesto-body at 11px on mobile is small. The manifesto-word at 20px serif is fine, but the body text beneath it could benefit from bumping to 12px on mobile.
- **The hero-bar items at 375px use `grid-template-columns: repeat(2, 1fr)` — the 4 division labels (Carbon, Chrome, Shop Space, Campus) wrap to 2x2.** The bar-val at 26px serif and bar-key at 7px mono are readable, but "Shop Space" and "Website Platform" may feel cramped in a half-width cell at 375px. The screenshot confirms this looks acceptable but tight.
- **No hamburger menu.** The nav-right links ("Objects" and "About") remain visible as tiny 8px text at all widths. At 375px with 16px side padding, this works because there are only 2 links, but if more links are ever added, there's no mobile nav pattern in place.
- **The philosophy section ghost text ("Build") at `font-size: 160px` at 480px may overflow.** The CSS does have `overflow: hidden` on `.philosophy`, but the text starts at `left: -20px` which could cause rendering issues on some mobile browsers.
- **Footer links at 11px with 12px margin-bottom may be tight for fat-finger tapping.** The touch target media query covers `.f-col a` with 44px min-height, but only on `(hover: none) and (pointer: coarse)` devices. Some tablets with stylus support may not match this query.
- **No `font-size: 16px` on inputs.** There are no inputs on this page, so no iOS zoom issue, but this is worth noting if a contact form is ever added.

### Specific Fixes
1. Bump `.manifesto-body` to 12px at the 480px breakpoint
2. Add a `@media (max-width: 480px)` rule for `.hero-bar .bar-val { font-size: 22px }` to prevent cramping
3. Consider adding a minimal hamburger pattern at 480px even if currently unnecessary, for future-proofing
4. Increase footer link `margin-bottom` from 12px to 16px on mobile for better tap spacing

---

## Critic 5 — Performance

**Score: 8/10**

### What's Good
- Single static HTML file, 1330 lines, no framework, no build step. This is ideal.
- Zero external JS. The only script is 9 lines of IntersectionObserver for scroll reveals.
- Zero images. The entire page is CSS-only visuals.
- JSON-LD is present and correct for SEO.
- `preconnect` to Google Fonts is included.
- Grain overlay uses an inline SVG data URI, avoiding an extra network request.
- The marquee uses CSS animation only, no JS.
- All animations use `transform` and `opacity` — composited properties that don't trigger layout/paint.

### What's Wrong
- **Fonts are NOT preloaded.** The page loads 3 font families (Cormorant Garamond at 7 weights, IBM Plex Mono at 4 weights, Montserrat at 7 weights) via a single Google Fonts CSS link. That's ~18 font files potentially downloaded. There is a `preconnect` but no `preload` for the critical font CSS. On slow connections, this means a flash of unstyled text (FOUT) or invisible text (FOIT) for up to 2-3 seconds.
- **Too many font weights loaded.** Cormorant Garamond loads weights 300, 400, 500, 600, 700 plus italic 300, 400, 500. The page only uses weights 300 and 400 (and italic). That's 5+ unused weight files downloaded. Same issue with Montserrat: loads 200-700 but only uses 300, 400, 500, 600.
- **The grain overlay uses `position: fixed` with `z-index: 9999`.** On some mobile browsers, fixed-position elements with high z-index that cover the entire viewport can cause compositing layer promotion for the entire page, which increases memory usage. At 2.8% opacity this is lightweight, but it's still a full-viewport pseudo-element being composited on every frame during scroll.
- **No `<meta>` for `theme-color`.** Adding `<meta name="theme-color" content="#0D0D0F">` would make the browser chrome match the site on mobile.
- **No `loading="lazy"` concern** (there are no images, so this is N/A, but worth noting the page is image-free by design).

### Specific Fixes
1. Trim the Google Fonts URL to only the weights actually used: `Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&IBM+Plex+Mono:wght@300;400&Montserrat:wght@300;400;500;600`
2. Add `<link rel="preload" as="style" href="[google-fonts-url]">` for above-the-fold font loading
3. Add `<meta name="theme-color" content="#0D0D0F">`
4. Consider adding `font-display: swap` fallback (Google Fonts includes this via `&display=swap` which is already present — good)

---

## Summary Table

| Critic | Area | Score |
|--------|------|-------|
| 1 | Visual Design | 8/10 |
| 2 | Brand Consistency | 7/10 |
| 3 | Audience Fit | 9/10 |
| 4 | Mobile (375px) | 7/10 |
| 5 | Performance | 8/10 |
| **Average** | | **7.8/10** |

---

## TOP 5 FIXES to Reach 9/10 Average

### 1. Fix the gold color to match the brand system (Critic 2 — biggest single issue)
Change `--gold: #F0B429` to `--gold: #b8965a` and `--gold-hi: #FFD060` to `--gold-hi: #d4aa6a`. Also update `--gold-lo` and `--gold-ghost` rgba values to use `184,150,90` instead of `240,180,41`. This alone fixes the "feels like a different brand" problem.

### 2. Fix the mono font to Courier Prime (Critic 2)
Replace `IBM+Plex+Mono` with `Courier+Prime` in the Google Fonts import and change `--mono: 'IBM Plex Mono', monospace` to `--mono: 'Courier Prime', monospace`. This aligns with both the storefront and the cc-final reference.

### 3. Darken the base colors to match (Critic 2)
Change `--void` from `#0D0D0F` to `#060606`, `--deep` from `#111113` to `#0a0a0a`, `--carbon` from `#161618` to `#0e0e0e`, and `--plate` from `#1C1C1E` to `#141414`. These are the exact values from cc-final.html.

### 4. Improve mobile typography and spacing (Critic 4)
Add to the `@media (max-width: 480px)` block: bump `.manifesto-body` to 12px, reduce `.hero-bar .bar-val` to 22px, increase footer link spacing to 16px margin-bottom. These small changes prevent the "cramped" feeling on 375px devices.

### 5. Trim font weight payload (Critic 5)
Reduce the Google Fonts URL from ~18 font files to ~10 by only requesting weights actually used. Change the import to: `Cormorant+Garamond:ital,wght@0,300;0,400;0,700;1,300;1,400&Courier+Prime:wght@400&Montserrat:wght@300;400;500;600&display=swap`. Add `<meta name="theme-color" content="#060606">` while in the `<head>`.

---

**Bottom line:** The page is architecturally solid and the copy is excellent for the audience. The main gap is brand token alignment — the gold, the mono font, and the base darkness are all shifted from the established system. Fix those three CSS variables and this page goes from "looks like a related project" to "this is unmistakably the same brand." The mobile and performance issues are minor polish.
