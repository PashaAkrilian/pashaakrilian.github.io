# Fix Log — "Open It on Your Phone"

**Live URL:** https://pashaakrilian.github.io/
**Date:** 17 Aug 2026
**Files touched:** `styles.css`, `index.html`, `ecosentra.html`, `siaga.html`, `nemotron.html`, `README.md`

Verified on a real viewport via headless Chrome at phone (390px), tablet (768px), and desktop (1280px) widths, with JS layout measurement for horizontal overflow and tap-target size. No images in the site are oversized (the only image, `siaga-dashboard.png`, is 88 KB / 1280×592 and already crisp).

## Mobile layout

| Broken | Changed |
| --- | --- |
| Nav links wrapped awkwardly on phones — left-aligned cluster, cramped tap targets (~14px tall). | Nav becomes a centered column under 600px; link font bumps to 1rem with `10px 8px` padding → ≥44px tall tap targets. |
| Social icon buttons were *shrunk* to 40×40 on small screens, below the 44px touch guideline. | Removed the shrink; social links stay 44×44 on every screen. |
| Brand link had a ~24px-tall hit area. | Added vertical padding → ~44px tall tap target. |
| Case pages used 24px side padding on phones, squeezing tables and charts. | Padding drops to 16px under 480px. |
| Wide tables needed a `min-width`, but horizontal scroll was clunky on iOS. | `.table-scroll` gets `-webkit-overflow-scrolling: touch` for momentum scrolling. |
| Contact "Send message" button was narrow and easy to miss on phones. | Becomes full-width under 480px. |

## Readability & accessibility

| Broken | Changed |
| --- | --- |
| No base `line-height` — paragraph rhythm varied across pages. | `body` now uses `line-height: 1.5`. |
| Form inputs used 0.95rem font → **iOS auto-zooms on focus**, breaking the mobile form flow. | Inputs/textarea bumped to 1rem (≥16px stops the zoom) plus `-webkit-appearance: none`. |
| Table headers at 0.7rem (11px) were hard to read on mobile. | Headers raised to 0.75rem. |
| `status-tag.planned` had `opacity: 0.75`, dropping contrast below 4.5:1 on its tiny text. | Removed the opacity; tag now meets AA contrast. |
| Metric-chart baseline bar labels were dark-on-blue at 4.29:1 (below AA). | Baseline blue lightened `#4E7FB8 → #5789C4` → 4.91:1 (legend, bars, and palette all updated). |
| Case-study table headers/cells, muted text, and accent links all verified against AA. | No change needed — contrast already passed (all ≥4.5:1). |

## Images & performance

| Broken | Changed |
| --- | --- |
| SIAGA screenshot had no `width`/`height`, causing layout shift on slow mobile loads. | Added `width="1280" height="592"` and `loading="lazy"`. |
| — | Confirmed no oversized assets: the only image is 88 KB and displays crisply (1280px source rendered down to ~358px on phones). |

## Links

| Check | Result |
| --- | --- |
| All internal links (`index.html`, `ecosentra.html`, `siaga.html`, `nemotron.html`, `#contact`) | All resolve; navigation verified identical on every page. |
| GitHub repos (SIAGA, Nemotron, EcoSentra) | All return 200. |
| SIAGA live demo (`frontend-nu-silk-76.vercel.app`) | Loads (title confirmed). |
| GitHub / LinkedIn / CV.pdf / mailto / formsubmit.co | All valid; `CV.pdf` present. |
| README live URL pointed to the stale `/Ship-the-Ugly-One/` path (404). | Corrected to `https://pashaakrilian.github.io/`. |

## Verification (post-fix, measured in a real browser engine)

- Horizontal overflow: **0px on all pages at 390 / 768 / 1280px.**
- Base font-size: 16px on every page.
- Remaining sub-44px items are inline text links inside paragraphs (exempt from the WCAG 2.5.8 target-size rule) and desktop nav links at 34px (above the 24px AA minimum).
- All 4 HTML files parse cleanly.

**Deploy note:** changes go live when the modified files are committed and pushed to `main` (GitHub Pages source).
