---
name: agent-managed-indexes
description: Use when building or maintaining a markdown routing surface that maps natural-language triggers to actions and the agent is expected to both read and write the index.
---

# Agent-Managed Indexes

Use this skill when a project needs a persistent, human-readable routing surface that the agent can maintain over time. The index should help the agent decide what to load, what to route, and what to consolidate next.

## Stance

An agent-managed index is a routing surface, not a database. It is useful because it is readable by humans, traversable by agents, and auditable through git diffs.

The index should return a bounded candidate set, not one magical answer. The point is to improve activation and routing, not to bury the agent in a deep hierarchy.

Keep the structure shallow. Keep route files simple. Keep the maintenance cycle explicit.

## When To Use

Use this skill when:

- the agent needs a reusable routing table for recurring work;
- the project has multiple routable concerns and the best next area is not obvious;
- routing knowledge must be editable by the agent itself;
- the index should help with discovery, not just storage;
- consolidation, archiving, or route rewiring is part of the work.

Do not use this skill for every collection of notes. If a flat index would add more ceremony than value, do not force it.

## Core Workflow

1. Read `INDEX.md` first.
2. Scan route files for trigger conditions that match the current context.
3. Rank the matching routes by specificity and priority.
4. Follow the best candidate route.
5. Use wikilinks for related routes or sub-routes when they help navigation.
6. Update consolidation notes after using or changing a route.
7. If routing behavior has shifted, rewrite the index entry point.

## Suggested Directory Shape

```text
index/
  INDEX.md
  routes/
    route-a.md
    route-b.md
  meta/
    consolidation-log.md
```

## Route File Shape

Route files should keep the trigger logic and the action close together.

Typical contents:

- natural-language trigger conditions;
- a short description of when the route applies;
- the action the agent should take;
- optional wikilinks to related routes;
- consolidation notes or usage notes if the route is maintained over time.

## Maintenance Rules

- Merge overlapping routes rather than duplicating them.
- Archive stale routes instead of keeping everything forever.
- Keep the entry point current when the routing strategy shifts.
- Detect cycles in wikilink traversal and break them.
- Prefer a semantic candidate-set activation step over rigid keyword matching at the entry point when scale justifies it.

## Quality Bar

- The index should help the agent know what to do next, not just where to file things.
- Route names and triggers should be understandable without hidden context.
- The structure should stay shallow enough that it remains maintainable.
- Every change should leave an audit trail the next agent can inspect.
