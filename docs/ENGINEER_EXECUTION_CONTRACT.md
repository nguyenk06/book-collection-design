# Engineer Execution Contract

This is the concise authoritative contract for Engineer execution. It supplements the [Handoff Protocol](HANDOFF_PROTOCOL.md); briefs still define scope and authority. Engineer must read this contract during `!init`, `!brief`, `!run`, post-compaction recovery, and replacement-thread initialization.

## Active-run invariant

Once `!run` is active, its authorization persists until the accepted objective is complete, `!drain`, `!stop`, the 15% floor/window boundary, or a genuine stopping condition below. Intermediate progress is nonterminal.

Engineer must not end the turn merely to report progress, a successful checkpoint, an ordinary lint/test/build failure, a recoverable tool failure, or an available next action. Emit concise progress updates while work continues; they do not request another Product Owner message. Never ask “continue?” for already-authorized work. A repeated `!run` is not required after ordinary remediation, validation, or a recoverable tool failure.

If active authority, sufficient capacity, and an in-scope next action remain, continue before producing a final workflow response.

## Mandatory pre-final continuation test

Before ending any active `!run` turn, evaluate all seven questions:

1. Is `!run` still active?
2. Does accepted scope remain unfinished?
3. Is the next action already authorized?
4. Does remaining capacity preserve the 15% floor?
5. Has the applicable three-attempt boundary actually been exhausted?
6. Is another independent authorized workstream eligible?
7. Is the problem limited to one tool/action rather than the whole workstream?

If any safe authorized continuation exists, continue instead of returning control.

## Terminal stopping conditions

A final response during active `!run` is allowed only when one of these is true:

- The accepted objective is complete.
- `!drain` or `!stop` applies.
- The 15% floor or five-hour window boundary is reached.
- The third substantive approach to the same problem failed.
- A genuine scope, safety, production, destructive-action, privacy, security, source-identity, or authority boundary is reached.
- A cross-cutting system limitation has no brief-authorized fallback.
- No eligible authorized work remains.

## Progress and terminal responses

- **`PROGRESS UPDATE — NONTERMINAL`**: a brief update emitted while tools/work continue. It expects no new Product Owner prompt and does not require the full canonical footer.
- **`TERMINAL WORKFLOW RESPONSE`**: completion, genuine blocker, reset boundary, explicit stop/drain, or no remaining eligible work. It requires exactly one canonical footer and the applicable sanitized transport handoff.

Before writing a terminal transport artifact, reserve its canonical footer skeleton at the bottom. After saving, reopen the artifact tail and verify that its last non-comment block contains exactly one footer form; `TL;DR` and `ACTION` are present; single-owner and parallel-owner forms are not mixed; and the named owner can perform the action. Only then may Engineer send the terminal chat response. The chat footer never substitutes for the file footer. If a saved artifact lacks the footer, preserve it unchanged and create a uniquely named formatting-only superseding report; do not repeat implementation, validation, Site, or production work. Never use `NEXT OWNER: ENGINEER` to end an active run when Engineer can continue immediately. Use `PLANNER` only for a genuine unresolved Planner Inbox decision, `DESIGNER` only when an Engineer artifact genuinely awaits intake, and `EXTERNAL/WAIT` only with an objective resume condition.

## Tool failures and attempts

A timeout, truncated output, lost controller result, access denial, failed lint/test/build, or missing PID blocks only that exact action unless evidence proves a cross-cutting hazard. Ordinary local failures remain within the accepted run.

Use up to three distinct brief-authorized substantive approaches. Do not escalate after Approach 1 merely because it failed. A verification rerun, typo/syntax correction, or trivial command repair is not a new substantive approach. Never improvise an unapproved elevated, destructive, production, dependency, configuration, or source-changing fallback. Briefs should provide a prioritized fallback ladder when predictable tool limitations exist.

## Brief and run separation

`!brief` accepts a new brief. A separate initial `!run` activates it. After activation, no additional `!run` is required for progress, checkpoints, retries, ordinary remediation, validation, or continuation inside the same accepted slice. Another command is required only after an actual stop/reset boundary, a new brief outside the active slice, or a new authority gate.

## Replacement continuity

A replacement does not reset attempts, transfer unsaved source automatically, or inherit authority by implication. Before replacement, Engineer creates the private local continuity artifact and a separate sanitized Designer handoff. The successor independently verifies actual source, repository, branch, HEAD, worktree state, candidate identity, authority, attempts, processes, dependencies, and remaining validation before accepting a superseding brief. Before ending its read-only `!init`, the successor must write one sanitized `INITIALIZATION / CONTEXT VERIFICATION` report to shared local `inbox/`. The terminal chat footer never substitutes for this artifact; Designer must process it before `!brief` acceptance.
