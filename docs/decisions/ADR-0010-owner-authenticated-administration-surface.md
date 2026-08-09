# ADR-0010: Owner-Authenticated In-Site Administration Surface

## Status

Accepted

## Context

Version 18 exposes owner-protected migration-bridge APIs, but two direct Engineer invocation attempts ended before application execution. A read-only investigation verified that normal owner mutations and bridge routes share the same server-side authorization helper, Site worker, and managed bindings. Normal Site UI requests use a proven same-origin browser path.

## Decision

Provide a small permanent owner-authenticated administration surface inside the Site for bridge schema status, private structured export, separately approved schema upgrade, and verification.

- Reuse the existing same-origin HTTP/JSON APIs and server-side owner authorization.
- Treat client-side visibility as convenience only; the server remains authoritative.
- Require deliberate confirmation and same-origin/CSRF protection before a schema-changing request.
- Keep status, export, upgrade, verification, final Shopping publication, smoke testing, and destructive recovery independently authorized.
- Keep migration and export business logic in testable server modules rather than the UI.
- Do not implement an authentication bypass, embed or disclose owner credentials, forward session material, impersonate the owner, or create an Engineer credential path.

## Consequences

- The Product Owner operates privileged controls through their authenticated Site session; Engineer may implement and validate the surface but receives no owner authentication material.
- Anonymous and non-owner requests must receive no administrative data or capability.
- The surface reduces dependence on direct Engineer endpoint invocation while preserving portable API and business-logic boundaries.
- Approval of this architecture does not authorize production requests, export, migration, publication, verification, restore, or destructive action.
- The bridge remains temporary infrastructure even though the narrow administration surface may remain available for later owner operations.

## Future considerations

Reassess the surface after Shopping activation. Retain only controls with continuing operational value, without weakening authentication or the independent production gates.
