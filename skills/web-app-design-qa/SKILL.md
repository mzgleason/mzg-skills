---
name: web-app-design-qa
description: "Playwright-first frontend QA for agents validating their own web app changes. Use when an agent has modified UI code and must actively check in a browser whether the result is visually correct, responsive, usable, and regression-safe before reporting completion."
---

# Web App Design QA

Use Playwright to actively inspect frontend changes in a running app before declaring the work done.

Default behavior: verify in the browser, not just by reading code or trusting screenshots from the build system.

If the app is not already running, start or reuse the local dev server first. If the relevant route is unknown, identify it from the codebase before opening the browser.

## Core Principle

Agents should treat visual QA as part of implementation, not as optional follow-up.

After frontend edits:

1. open the changed surface in a browser
2. inspect the actual rendered result
3. interact with key states
4. look for regressions
5. fix issues when found
6. re-check before finishing

## When To Use This Skill

Use this skill when:

- an agent changed HTML, CSS, React, Vue, component styling, layout logic, or frontend behavior
- a page, component, dashboard, form, or flow needs visual verification
- responsive behavior, alignment, spacing, hierarchy, or polish matters
- the user asks whether the UI "looks right", "works correctly", or is "ready"

Do not use this skill for backend-only work with no user-visible surface.

## Workflow

1. **Identify the changed surface**
   - Determine which page, route, component, modal, or flow was changed.
   - Prefer checking the exact affected surface instead of browsing randomly.

2. **Open the app with Playwright**
   - Use Playwright or an equivalent browser automation tool to load the local or deployed page.
   - Prefer a stable local URL when available.
   - Wait for meaningful content, not just initial HTML.

3. **Run visual QA on the happy path**
   - Inspect the changed surface at desktop first.
   - Check layout, spacing, hierarchy, typography, color use, contrast, and obvious polish issues.
   - Confirm the intended user action still works.

4. **Run breakpoint checks**
   - Always check both:
     - desktop
     - mobile
   - Check tablet too when the surface is complex or clearly used at intermediate widths.
   - Focus on clipping, overflow, wrapping, cramped spacing, collapsed hierarchy, and unusable controls.

5. **Run interaction and state checks**
   - Exercise the core changed interaction.
   - Check hover, focus, active, disabled, loading, empty, error, and success states when applicable.
   - If the change affects a flow, verify the flow end to end, not just the first screen.

6. **Check implementation quality signals**
   - Watch for console errors and obvious failed requests.
   - Look for broken images, layout shifts, flicker, z-index problems, and inaccessible contrast.
   - Validate that new components feel consistent with the surrounding product unless the task intentionally changes the visual system.

7. **Capture evidence**
   - Save screenshots when useful for review or comparison.
   - Prefer before/after or desktop/mobile captures when they clarify the result.

8. **Fix and re-check**
   - If issues are found, fix them and repeat the browser QA loop.
   - Do not report success based only on code inspection after a visual bug was discovered.

## QA Checklist

Use the checklist in [references/qa-checklist.md](references/qa-checklist.md) during review. At minimum, explicitly check:

- layout and alignment
- spacing and hierarchy
- desktop rendering
- mobile rendering
- responsiveness
- changed interaction behavior
- empty, loading, and error states when relevant
- console or runtime issues

## Output Guidance

When reporting results, use this structure:

- `Surface checked`
- `What was verified`
- `Issues found`
- `Fixes applied`
- `Evidence`
- `Residual risk`

If no issues are found, say that explicitly and mention what was actually checked. Do not claim broad QA coverage if only one screen was opened.

## Standards

- Prefer concrete findings over vague approval language.
- Be suspicious of screenshots that hide hover, focus, overflow, or off-screen issues.
- If the user asked for a polished UI, judge polish as part of correctness.
- If a route requires setup data or authentication, state the limitation clearly and test as far as possible.

## Example

User request:

`I updated the dashboard cards and filters. Check that the frontend changes look good.`

Good behavior:

1. identify the dashboard route
2. open it with Playwright
3. always check both desktop and mobile
4. exercise the filter interaction
5. inspect hover/focus and loading states
6. note any layout or console problems
7. fix issues if present
8. report what was verified with screenshot evidence if useful
