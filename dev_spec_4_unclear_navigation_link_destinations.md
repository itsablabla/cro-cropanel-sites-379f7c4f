# Unclear navigation link destinations — dev spec
Site: perplexity.ai · Priority 4 · Medium · Effort: Low (0.5-2 days)

## Problem
Top navigation items lack descriptive labels, making it hard for users to predict where links lead.

## Evidence (from the live site)
> New ⌃I Computer Computer Artifacts Artifacts Customize Customize Projects Projects

## Current state
notes: Navigation items like 'New', 'Computer', 'Artifacts', 'Customize' lack descriptive labels.

## Required change
notes: Add descriptive sublabels or tooltips to each navigation item.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add descriptive sublabels or tooltips to each navigation item.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unclear_navigation_link_destinations` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
