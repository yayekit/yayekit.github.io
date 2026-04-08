# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website for Keith Yemelianovskyi, hosted via GitHub Pages at `yayekit.github.io`.

## Architecture

Single-page static site — no build step, no bundler, no framework. All markup, styles, and scripts live in `index.html`. GitHub Pages serves the `main` branch root directly.

## Development

- **Preview locally:** Open `index.html` in a browser (no server needed).
- **Deploy:** Push to `main` on `github.com/yayekit/yayekit.github.io` — GitHub Pages auto-deploys.

## Conventions

- Keep everything in a single `index.html` (inline CSS/JS) unless complexity demands splitting.
- Support dark mode via `prefers-color-scheme` CSS media query.
- No external dependencies or CDN links — zero-dependency site.
- Resume PDF (`keith_yemelianovskyi_resume.pdf`) is the source of truth for content.
