# Web App Design QA Checklist

Use this checklist when reviewing frontend changes in the browser.

## 1. Layout

- Is the changed surface aligned correctly?
- Are sections, cards, and controls spaced consistently?
- Is anything clipped, overlapping, or mis-sized?
- Does the hierarchy read clearly at a glance?

## 2. Responsiveness

- Always verify the layout on desktop.
- Always verify the layout on mobile.
- If the surface is complex, does it still work on tablet?
- Do text, buttons, tables, and filters wrap or collapse cleanly?
- Use standard defaults unless there is a reason not to:
  - desktop `1440x900`
  - mobile `390x844`

## 3. Interaction

- Does the changed interaction behave as intended?
- Do hover and focus states still appear correctly?
- Are disabled states obvious?
- Do controls remain usable with realistic content lengths?

## 4. State Coverage

- Loading state
- Empty state
- Error state
- Success state

Check only the states that are relevant, but do not ignore obvious state regressions.

## 5. Realistic Content

- Long labels
- Empty values
- Large numbers
- Multiple chips, filters, or tags
- Dense tables or long row values

Do not trust a UI that only looks good with ideal placeholder content.

## 6. Runtime Quality

- Console errors
- Failed requests
- Broken images or icons
- Layout shift or flicker
- Z-index or overlay issues

## 7. Evidence

- Desktop screenshot
- Mobile screenshot
- Short video clip if validating animation or motion behavior

If evidence could not be captured, state why.

## 8. Product Fit

- Does the changed UI still feel consistent with the surrounding app?
- If the task was intentionally more expressive, does it still feel deliberate rather than broken?
- Does the result meet the user’s bar for polish, not just bare functionality?

## 9. Reporting

When finishing, report:

- status: pass / pass with minor issues / fail
- what you checked
- what issues you found
- what you fixed
- what remains unverified
