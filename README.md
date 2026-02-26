# design-palette
# Mobile Design System — Foundations
Version: v1.0  
Status: Living Document  
Owner: [Your Name]  
Last Updated: [DD.MM.YYYY]

---

# 1) Purpose

This document defines the foundational design rules for all mobile applications
developed under this product ecosystem.

It ensures:

- Visual consistency
- Scalability across multiple apps
- Faster feature development
- Easier theming & multi-brand support
- Design–Code alignment

This is a **mandatory reference document** for all UI implementation.

---

# 2) Brand Layer

## 2.1 Brand Identity

Product Name: [App Name]  
Brand Tone (3 adjectives):  
- Example: Minimal / Structured / Reliable  

## 2.2 Design Philosophy

- Clarity over decoration
- Function before aesthetics
- Touch-first ergonomics
- Accessibility-first
- Consistency over creativity

---

# 3) Color System

⚠️ Raw HEX usage inside components is forbidden.  
Only semantic tokens may be used.

---

## 3.1 Primary Palette

| Token | Value | Usage |
|-------|-------|-------|
| color.primary | #4F46E5 | Main CTA buttons |
| color.primary.soft | #EEF2FF | Soft background tint |
| color.primary.dark | #3730A3 | Pressed state |

---

## 3.2 Neutral Palette

| Token | Value | Usage |
|-------|--------|-------|
| color.background | #FFFFFF | App background |
| color.surface | #F9FAFB | Cards / sections |
| color.border | #E5E7EB | Dividers |
| color.text.primary | #111827 | Main text |
| color.text.secondary | #6B7280 | Secondary text |
| color.text.muted | #9CA3AF | Metadata |

---

## 3.3 Semantic Colors

| Token | Value | Usage |
|-------|--------|-------|
| color.success | #10B981 | Positive state |
| color.warning | #F59E0B | Attention |
| color.error | #EF4444 | Error state |
| color.info | #3B82F6 | Informational |

---

## 3.4 Dark Mode Tokens

| Token | Value |
|-------|--------|
| color.background.dark | #0F172A |
| color.surface.dark | #1E293B |
| color.text.primary.dark | #F8FAFC |
| color.border.dark | #334155 |

---

# 4) Typography System

## 4.1 Font Family

Primary Font: Inter  
Fallback:
- iOS → System
- Android → Roboto

---

## 4.2 Type Scale

| Token | Font Size | Weight | Usage |
|-------|-----------|--------|-------|
| text.display | 32 | Bold | Large headers |
| text.h1 | 28 | Bold | Page title |
| text.h2 | 22 | SemiBold | Section title |
| text.h3 | 18 | SemiBold | Card title |
| text.body | 16 | Regular | Default |
| text.caption | 14 | Regular | Secondary |
| text.small | 12 | Regular | Metadata |

---

## 4.3 Line Height Rules

Line height is defined as a multiplier (unitless).

- Headings → 1.2
- Body → 1.4
- Small text → 1.3

Example:

If font-size = 16  
Line-height = 1.4  

Computed line-height = 22.4px

Implementation example (React Native):

fontSize: 16  
lineHeight: 16 * 1.4

---

# 5) Spacing System

4pt Grid System

| Token | Value |
|-------|--------|
| space.xs | 4 |
| space.sm | 8 |
| space.md | 16 |
| space.lg | 24 |
| space.xl | 32 |
| space.2xl | 40 |

Rules:

- No arbitrary spacing values allowed.
- Only spacing tokens may be used.
- Layout rhythm must follow grid consistency.

---

# 6) Radius System

| Token | Value |
|-------|--------|
| radius.sm | 6 |
| radius.md | 12 |
| radius.lg | 20 |
| radius.full | 999 |

Usage:

- Buttons → radius.md
- Cards → radius.md
- Pills / tags → radius.full

---

# 7) Elevation System

## iOS Shadow Levels

- shadow.sm → Cards
- shadow.md → Modals
- shadow.lg → Floating elements

## Android Elevation

| Token | Value |
|-------|--------|
| elevation.sm | 2 |
| elevation.md | 4 |
| elevation.lg | 8 |

---

# 8) Border System

| Token | Value |
|-------|--------|
| border.thin | 1 |
| border.thick | 2 |

---

# 9) Motion Guidelines

| Token | Duration |
|-------|-----------|
| motion.fast | 150ms |
| motion.normal | 250ms |
| motion.slow | 350ms |

Default easing: ease-in-out

Guidelines:

- Motion must communicate hierarchy.
- No decorative animation without functional purpose.
- Loading indicators < 500ms must not block UI.

---

# 10) Accessibility Requirements

- Minimum touch target: 44x44
- Contrast ratio: WCAG AA minimum
- Font scaling must be enabled
- Error states must include text + visual indicator
- No information should rely on color only

---

# 11) Theming Strategy

This system supports:

- Light mode
- Dark mode
- Future multi-brand support

All components must consume semantic tokens.

No hardcoded values allowed.

---

# 12) Implementation Guidelines

Recommended structure:

/design  
  ├── foundations.md  
  ├── tokens.json  
  ├── components.md  

All UI must reference tokens from:

/src/theme/tokens.ts

---

# 13) Version Control

Every visual change must update this document.

Version bump required for:

- New color token
- Typography scale change
- Spacing modification
- Radius adjustment

---

# End of Foundations Document
