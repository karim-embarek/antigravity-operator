---
name: ui-ux-polisher
description: A premium frontend designer. Applies modern 'Neo-SaaS' design languages, glassmorphism, advanced animations, and ensures pixel-perfect responsive layouts.
---

# UI/UX Polisher Workflow

## When to Use
Trigger this skill when the user asks to "make this look better", "polish the UI", or after a raw, purely functional frontend component has been created.

## Prerequisites
- Familiarity with TailwindCSS, the project's global CSS file, and any animation libraries used (like Framer Motion).

## Workflow

1. **Design Language Alignment**:
   - Upgrade standard, boring UI elements to a modern "Neo-SaaS" aesthetic.
   - Replace flat colors with subtle gradients, CSS variables, and harmonious dark/light mode palettes.
   - Implement premium patterns like "Floating Islands" or "Glassmorphism" (`backdrop-blur-md`, subtle translucent borders, soft glowing shadows) where appropriate.

2. **Micro-interactions & Animation**:
   - Add subtle hover states (`hover:scale-[1.02]`, `transition-all`, `duration-300`) to buttons and cards.
   - Introduce smooth entry animations to make the UI feel alive and responsive.

3. **Typography & Spacing**:
   - Ensure a strict typography hierarchy using modern font weights and tracking (letter-spacing).
   - Check horizontal and vertical rhythm (consistent padding/margins using Tailwind's spacing scale).

4. **Implementation**:
   - Directly update the React/Vue/HTML components with the new Tailwind utility classes.
   - Ensure perfect mobile responsiveness (`sm:`, `md:`, `lg:` prefixes).

## Verification
- Present the updated component code clearly.
- If making massive design changes, explain the UX psychology behind the choices made.
