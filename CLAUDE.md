# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A collection of standalone single-file HTML tools. Each tool is entirely self-contained — no build system, no dependencies, no frameworks. Open any `.html` file directly in a browser.

## Architecture

Each tool is a single `.html` file with inlined CSS (`<style>`) and JavaScript (`<script>`). There are no shared files, modules, or assets.

**Conventions observed across tools:**

- CSS custom properties (`--var`) for theming, defined in `:root`
- CSS `@media print` for print-specific layout (hiding controls, removing shadows)
- State persisted to `localStorage` (user data) and `sessionStorage` (UI state like collapsed sections)
- No external JS dependencies; Canvas API used for image export where needed
- Inline SVG data URIs for favicons
- Responsive via flexbox/grid with `@media` breakpoints

## Existing tools

- `hfw-tracker.html` — Horizon Forbidden West quest tracker. Quest data is a static `CATEGORIES` array. Completion state lives in `localStorage`. Supports search, category filtering, and collapsible sections.
- `a4-image-layout.html` — Places two images onto an A4-sized page with a title. Exports via Canvas API at 3× scale (~288 DPI). Print support via `@media print`.
