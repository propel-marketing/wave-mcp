---
type: Policy
title: Generous Limits
description: Agent tooling is sized generously for real work — limits are ample by default, restrictions minimal, and tight caps need a specific reason.
publication_state: published
timestamp: '2026-11-04T01:01:32+00:00'
owner_role: CEO
---
# Generous Limits — Size Agent Tooling for Real Work (fleet protocol)

_Agency knowledgebase home: `agents/protocols/generous-limits.md` (fleet protocol). How limits are set in anything built for agents. Set by the CEO, 2026-11-03._

## Applies to

Every limit in agent tooling: payload and buffer sizes, timeouts, counts, quotas, retention, context and history bounds — in briefs the Coordinator writes and in implementations any agent builds.

## Rule

1. **Ample by default.** Size each limit for the agent's real, extensive work and for what the machine can reasonably support, with wide headroom — megabytes where a design reaches for kilobytes, minutes where it reaches for seconds.
2. **Never size to the test.** A limit chosen because the current case barely passes it is a defect, not a sizing. Passing values are evidence, not targets.
3. **Restrictions stay minimal.** A tight limit needs a specific reason — a real resource bound, or preventing catastrophic or irreversible harm (per [Directive Authoring](directive-authoring.md)). Absent one, loosen it.
4. **Briefs state it; builders audit it.** The briefer names the generous sizing expected. The builder checks every numeric limit it introduces or inherits against this protocol and reports each one kept, raised, or justified.

## Why

Agents do laborious, extensive work; tooling sized to the demonstration fails on the job. Observed 2026-11-03: a relay capped responses at 16 KB; normal session history grew past it in days and permanently wedged a production slot. Raising that cap to a barely-passing 50 KB would only have moved the failure — the correct size is megabytes, which the machine supports easily.

## Scope

- The rule text lives here only. Briefs and agent guidance files reference this protocol; they do not restate it.
- Deliberate design bounds set by the CEO (for example a concurrency cap chosen as policy) are decisions, not sizing — this protocol governs the limits nobody deliberately chose.
