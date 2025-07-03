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

## Accessibility Test Workflow (axe-core)

Use the following command to run accessibility checks on a specific example:

npx axe-cli <example-filename.html>

## Workflow
1. Given a component name or list of components, determine where is the source code responsible for them
2.Inspect source code of the components and especially onRender method. Look for html markup code and component templates. Inspect them for accessibility issues and attempt to fix them.
3.Given a component name or list of components, determine which examples/<component name/*.html file(s) render those components.
4 For each matched file:
 4.1 Run npm run axe -- <example subdirectory>/<example-filename.html>
 4.2 Review the corresponding a11y-reports/<example-filename>.json
5. If any violations are reported:
 5.1 Locate and modify the responsible component inside the src/ directory
 5.2 Immediately run npm run build after modifying any files in src/ to regenerate the bundled ext-all-debug.js
 5.3 Re-run the axe test with npm run axe to confirm the fix
 5.4 If the violations relate to any code that is located within the example directory, clearly say so and do not attempt to fix it in src/ directory
6. Repeat this cycle until axe reports 0 error violations for the example