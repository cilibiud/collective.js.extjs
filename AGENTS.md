# Project Agents.md Guide for OpenAI Codex

This Agents.md file provides comprehensive guidance for OpenAI Codex and other AI agents working with this codebase.

## Project Structure for OpenAI Codex Navigation

- `/js/extjs/ext-3.4.0/src`: Source code that OpenAI Codex should analyze and modify.

## Scope of Fixes
You Must Fix:
- All WCAG 2.2 Level AA (Double-A) accessibility requirements.
- Missing accessible names (aria-label, aria-labelledby, visible text)
- Improper roles or missing roles (role="button", role="presentation")
- Screen reader traps or invisible focusable elements
- Inputs missing labels
- Improper keyboard navigation and focus handling
- All other WCAG 2.2 requirements
- Any other highlighted violations in the axe reports

You Must NOT:
- Modify CSS, layout, spacing, colors, fonts, contrast
- Visually alter any component's appearance
- Refactor ExtJS internal API or change business logic unless required for accessibility
