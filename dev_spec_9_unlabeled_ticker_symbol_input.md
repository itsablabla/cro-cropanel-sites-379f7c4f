# Unlabeled ticker symbol input — dev spec
Site: perplexity.ai · Priority 9 · Medium · Effort: Low (0.5-2 days)

## Problem
The ticker input lacks a visible label or hint, adding friction for users wanting to look up another stock.

## Evidence (from the live site)
> NVIDIA Corporation NVDA · NASDAQ

## Current state
notes: Ticker symbol and price shown but no label or helper text.

## Required change
notes: Add visible label and helper text like 'Enter a stock symbol (e.g., AAPL)'.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add visible label and helper text like 'Enter a stock symbol (e.g., AAPL)'.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unlabeled_ticker_symbol_input` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
