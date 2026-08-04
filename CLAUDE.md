# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository overview

This repo contains a single static file, `index.html` — a "5-Digit Random Number Generator" web page. There is no build system, package manager, server, or test suite; the entire application is one self-contained HTML file with inline `<style>` and `<script>`.

## Development

There are no build/lint/test commands — open `index.html` directly in a browser to run it (e.g. `open index.html` or serve the directory with any static file server). Changes are made directly to `index.html` and verified by reloading the page.

## Architecture

- `index.html` is fully self-contained: markup, CSS, and JS all live in this one file.
- External dependencies are limited to Google Fonts (`VT323`, `DSEG7 Classic`) loaded via `<link>` tags — the `DSEG7 Classic` font is loaded but `VT323` is what's actually applied to `#number`.
- The "Generate" button triggers `generate()`, which runs a `setInterval` loop (60ms tick) that rapidly randomizes the displayed 5-digit number for a randomized 3–4 second duration ("rolling" effect) before settling on a final random value. A `rolling` flag guards against overlapping runs while the button is disabled mid-roll.
