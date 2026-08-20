# Ambiguous search input labels — dev spec
Site: perplexity.ai · Priority 2 · Medium · Effort: Low (0.5-2 days)

## Problem
Repeated placeholder text without a clear label confuses users about what the search input accepts, hurting conversion.

## Evidence (from the live site)
> What do you want to know?What do you want to know?What do you want to know? Ask anything…

## Current state
notes: Search box shows three stacked placeholder lines with similar phrasing.

## Required change
notes: Replace with a single explicit label such as 'Ask a question or search the web' and remove duplicates.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace with a single explicit label such as 'Ask a question or search the web' and remove duplicates.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_ambiguous_search_input_labels` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
