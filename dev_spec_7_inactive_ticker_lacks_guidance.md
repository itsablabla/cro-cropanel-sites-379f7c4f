# Inactive ticker lacks guidance — dev spec
Site: perplexity.ai · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
The inactive ticker page dead-ends users by stating the ticker is inactive without offering a search or alternative action, causing them to leave.

## Evidence (from the live site)
> This ticker is no longer active.

## Current state
notes: Page states ticker is no longer active but offers no input or next-step option.

## Required change
notes: Provide a search field or prominent link to search for another ticker directly on the page.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Provide a search field or prominent link to search for another ticker directly on the page.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_inactive_ticker_lacks_guidance` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
