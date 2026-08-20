# No trust signals on finance pages — dev spec
Site: perplexity.ai · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
Finance pages lack credibility markers near decision points, reducing user trust and hurting conversion.

## Evidence (from the live site)
> Cookie Policy
> Notable Price Movement
> Stories & Analysis
> Analyst Consensus
> Related Prediction Markets

## Current state
notes: No reviews, guarantees, security badges, or credibility markers near price and analysis content.

## Required change
notes: Add a trust strip with data-source citations, update timestamps, and a security badge near price and analyst consensus.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a trust strip with data-source citations, update timestamps, and a security badge near price and analyst consensus.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_trust_signals_on_finance_pages` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
