# ADR-0001: Purpose of This Repository

## Status

Accepted

## Context

Product direction, architecture, and implementation can change at different rates. A durable source of truth is needed for future human and AI contributors without coupling design history to application code.

## Decision

This repository is the permanent Markdown-first home for Book Collection System vision, architecture, roadmap, feature boundaries, and architectural decisions. The application is implemented elsewhere.

## Consequences

- Design remains accessible and reviewable independently of the application stack.
- Implementation changes that affect architecture require coordinated documentation updates.
- This repository must avoid becoming a second implementation repository.
- Some current-state facts depend on verification against the application repository.
