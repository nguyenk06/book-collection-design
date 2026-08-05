# ADR-0007: Separate Shopping Persistence Before UI Work

## Status

Accepted

## Context

Shopping Mode is the highest-priority user workflow, but `books` cannot represent purchase price, date, business, and condition history safely. Building the interface first would deepen mixed responsibilities and accumulate financial data without relational integrity.

## Decision

Implement Shopping persistence before redesigning the UI. Store purchases separately from books, normalize Businesses, and store collection target price on `collections`. Use integer cents for money; calculate historical averages from purchase rows rather than storing them.

## Consequences

- Books no longer need to absorb transaction history.
- Businesses can be reused consistently across purchases.
- Target price remains collection policy rather than a book or purchase fact.
- The migration must preserve existing ownership data and define how ownership relates to purchases.
- Shopping UI work waits for persistence, integrity, and focused tests.
