# AGENTS.md

## Project Overview

**plus-ultra** is an open source CSS/Sass library that provides Material Design–inspired components built on top of **Bulma CSS**.

The project intentionally:

- uses **Bulma only for layout, helpers, and base structure**
- implements **Material Design visuals and behaviors purely with CSS/Sass**
- does **not** use JavaScript for component logic
- treats Bulma as an external dependency, never as a fork or modified source

The final output of the project is a compiled CSS file located in `dist/plus-ultra.css`.

---

## Core Principles

When working on this codebase, always respect the following principles:

1. **Bulma must never be modified directly**
   - Do not edit files inside `node_modules/bulma`
   - All customization must happen through Sass variables, overrides, or additional components

2. **CSS/Sass only**
   - No JavaScript
   - No CSS-in-JS
   - No runtime logic

3. **Material Design is a visual language**
   - Focus on color systems, elevation, spacing, motion, and states
   - Avoid mimicking JS-heavy Material frameworks

4. **Compatibility with Bulma markup**
   - Existing Bulma class names and HTML structures should continue to work
   - Extensions should feel additive, not disruptive

---

## Technical Stack

- Package manager: **pnpm**
- CSS framework dependency: **Bulma (^1.x)**
- Preprocessor: **Dart Sass**
- Entry point: `src/sass/index.scss`
- Build output: `dist/plus-ultra.css`

Sass compilation uses `--load-path=node_modules` to resolve dependencies.

---

## Sass Architecture Guidelines

- Variables must be defined **before** importing Bulma
- Bulma should be imported once, from the main entry file
- Custom components should live in their own partials
- Overrides must be explicit and intentional

Preferred structure:

- Variables: design tokens, colors, elevation, transitions
- Bulma import
- Overrides of existing Bulma components
- New Material-inspired components

Avoid deeply nested selectors and excessive specificity.

---

## Design Philosophy

This project favors:

- clarity over cleverness
- explicitness over magic
- composability over monolithic components

Code should be readable by someone familiar with Bulma and basic Sass, without requiring framework-specific knowledge.

---

## What the Agent Should Avoid

- Introducing JavaScript or interactivity logic
- Rewriting Bulma components from scratch
- Tight coupling between components
- Overengineering abstractions
- Adding tooling not strictly necessary for a CSS library

---

## Goal

The goal of **plus-ultra** is to provide a clean, maintainable, and extensible Material-style layer on top of Bulma, suitable for real-world projects and easy adoption by existing Bulma users.
