# Ship the Ugly One

Personal portfolio site, deployed via GitHub Pages.

**Live:** https://pashaakrilian.github.io/

## About

I engineer reliable software for robots — from perception and motion control to system integration —
turning experimental hardware into robots that actually work outside the lab.

Currently transitioning: **ML Engineer → Robotics Software Engineer**

## Stack

Plain HTML + a shared `styles.css`, no build step, no dependencies. `index.html` is the homepage;
`ecosentra.html`, `siaga.html`, and `nemotron.html` are individual case study pages.

## Deploy

Push to `main`, then enable GitHub Pages in **Settings → Pages** (source: `main` branch, `/root`).
The repo is named `pashaakrilian.github.io`, so Pages serves it at the domain root (no `/repo-name/`
path segment) — that's what makes it a clean free subdomain instead of a project-pages URL.

## Analytics

Google Analytics 4 (`G-FHNJXX34TW`, property "Dimas Pasha Portfolio") via `gtag.js`, on every page.

## FlyRank graduate badge

Pending — FlyRank issues certificates/badges in early September 2026. Each page's footer has a
"FlyRank Graduate — pending" placeholder pill (`.grad-badge-pending` in `styles.css`) with an HTML
comment showing the exact markup to swap in once the real badge image + verification URL exist.
