# Web App Design QA Checklist

Use this checklist when reviewing frontend changes in the browser.

## 1. Layout

- Is the changed surface aligned correctly?
- Are sections, cards, and controls spaced consistently?
- Is anything clipped, overlapping, or mis-sized?
- Does the hierarchy read clearly at a glance?

## 2. Responsiveness

- Does the layout still work on desktop?
- Does it still work on mobile?
- If the surface is complex, does it still work on tablet?
- Do text, buttons, tables, and filters wrap or collapse cleanly?

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

## 5. Runtime Quality

- Console errors
- Failed requests
- Broken images or icons
- Layout shift or flicker
- Z-index or overlay issues

## 6. Product Fit

- Does the changed UI still feel consistent with the surrounding app?
- If the task was intentionally more expressive, does it still feel deliberate rather than broken?
- Does the result meet the user’s bar for polish, not just bare functionality?

## 7. Reporting

When finishing, report:

- what you checked
- what issues you found
- what you fixed
- what remains unverified
