# Omar.dev — Personal Website

A minimal, single-page personal website served from a custom domain. This repository is a fork of [gaby.dev](https://github.com/GitSquared/gaby.dev) (Gabriel Saillard's personal site) that is being actively developed as a personal homepage, blog, and resume presence for Omar Rashdan, deployed to the custom domain `omer.dev` (see `CNAME`).

## Overview

The site is a lightweight, dependency-light static page: a single `index.html` entry point styled with hand-written CSS, served by a static file server and deployed through Vercel. There is no build step, no framework, and no JavaScript framework runtime — just HTML, CSS, and a small inline script for Vercel Analytics.

The repository is a fork of the open-source `gaby.dev` project. The fork adds a `CNAME` record pointing the deployment at the custom domain `omer.dev`; the page content, styling, and redirect rules have since been fully personalized for Omar.

## Features

- **Single-page homepage** — hero heading, short bio, and a contact link rendered from static HTML (`public/index.html`).
- **Custom 404 page** — a styled not-found page with a link back to the homepage (`public/404.html`).
- **Desert dusk palette** — a deep charcoal background (`#0D1117`) with warm off-white text (`#D8CFC0`), amber-gold accents (`#E8A33D`), and teal highlights (`#2DD4BF`).
- **Animated visual identity** — a pure-CSS "painting" rendered from amber/teal gradients in the desert dusk palette, with a hue-shift glow animation and a custom SVG clip-path (`public/styles/index.css`).
- **URL redirects** — Vercel-level 302 redirects for short links (`/github`, `/linkedin`) pointing at Omar's accounts (`vercel.json`).
- **Search-engine hygiene** — `robots.txt` disallowing private assets and redirect targets.
- **Vercel Analytics** — page-view tracking via the Vercel Insights script.

## Tech Stack

- **Markup & styling** — Plain HTML5 and hand-written CSS (Poppins font from Google Fonts).
- **Local dev server** — [lite-server](https://github.com/johnpapa/lite-server) (BrowserSync-based static server) configured via `bs-config.js` to serve the `public/` directory and rewrite trailing-slash URLs to `index.html`.
- **Deployment** — [Vercel](https://vercel.com) (`vercel.json`, Vercel CLI as a dev dependency) with a custom domain from the `CNAME` file.

## Getting Started

The site is pure static content — no build step is required.

```bash
# Install the local dev server
npm install

# Serve the site locally (serves ./public on a local port)
npm run dev
```

Alternatively, open `public/index.html` directly in a browser, or serve the `public/` directory with any static file server.

## Deployment

Deployment is handled by Vercel:

- `vercel.json` defines the routing rules (redirects, filesystem handling, and a catch-all 404).
- The `CNAME` file binds the deployment to the custom domain `omer.dev`.
- The Vercel CLI (`vercel`) is included as a dev dependency for command-line deploys.

## Repository Layout

```
public/            Static site root (served as-is)
  index.html       Homepage (hero, bio, contact)
  404.html         Custom not-found page
  pgp-public.asc   PGP public key
  robots.txt       Crawler rules
  styles/          Hand-written CSS (index.css, 404.css, water.css)
  pics/            Favicons and background artwork
bs-config.js       lite-server configuration (baseDir: public)
vercel.json        Vercel routing and redirect rules
CNAME              Custom domain record (omer.dev)
```

## Notes

- This is a fork of the upstream `gaby.dev` project; the `package.json` name (`gaby.dev_tools`) is inherited from the upstream repository.
- The site is fully personalized: the homepage hero, bio, and contact link describe Omar's current work on Elmanssa, an Arabic-first (RTL) online learning platform, along with his ASP.NET Core 8.0 backend, Flutter, and n8n automation work.
- The Vercel redirects now point to Omar's own accounts (`/github` → `github.com/phlzas`, `/linkedin` → his LinkedIn profile). The upstream `/edex`, `/twitter`, `/hn`, and `/pgp` routes have been removed.