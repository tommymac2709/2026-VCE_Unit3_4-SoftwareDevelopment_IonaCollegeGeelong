# CSS Guide

This guide documents the styling system used across the site and how to apply it consistently.

## Brand Tokens

Use these CSS variables for consistent color and UI tone.

- Primary: `#442566` (`--md-primary-fg-color`)
- Primary light: `#5a3b7a` (`--md-primary-fg-color--light`)
- Primary dark: `#341a4c` (`--md-primary-fg-color--dark`)
- Accent: `#3990b0` (`--md-accent-fg-color`)
- Accent tint: `rgba(57, 144, 176, 0.15)` (`--md-accent-fg-color--transparent`)
- Gold highlight: `#eec33a` (`--gds-gold`)
- Grey utility: `#9c9fa1` (`--gds-grey`)

## Typography

- Headings `h1` and `h2` use `Philosopher`.
- Headings `h3` to `h6` use `Helvetica Neue`, `Helvetica`, `Arial`, `sans-serif`.
- Body text uses the default Material theme font stack.

## Links

- Default link color is the accent blue.
- Hover uses the primary purple for emphasis.

## Navigation

- Top navigation and header use the primary purple background.
- Active or hovered tabs use the gold highlight.

## Admonitions

Admonitions keep a clean white background with a color-coded left border:

- Default: primary purple
- Tip: accent blue
- Warning: gold highlight
- Info: grey utility
- Abstract: primary purple

## Table Of Contents

The right-hand table of contents uses a light grey bordered card with subtle hover and active states.

## Left Navigation

Left navigation sections and active links use distinct backgrounds and left borders for visual grouping.

## How To Extend

If you need to add custom styles:

- Use the existing CSS variables first.
- Avoid hardcoding new colors unless they are approved by the brand palette.
- Keep overrides scoped to `.md-typeset` or Material classes for predictable behavior.
