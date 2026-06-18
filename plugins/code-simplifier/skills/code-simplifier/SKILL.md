---
name: code-simplifier
description: Use when Codex should simplify, refactor, or clean up recently modified code while preserving exact behavior, especially after an implementation session, before commit, or when code has become overly complex, duplicated, deeply nested, or inconsistent with project conventions.
---

# Code Simplifier

Use this skill to refine code for clarity, consistency, and maintainability without changing what it does.

## Scope

- Focus on files changed in the current session or the user's explicitly named files.
- Preserve all behavior, public APIs, outputs, data formats, and side effects.
- Follow the nearest `AGENTS.md` and existing project style before applying general preferences.
- Keep changes surgical. Do not refactor unrelated old code.
- Prefer readable, explicit code over clever or highly compressed code.

## Workflow

1. Inspect the current diff and nearby code before editing.
2. Identify simplifications with a clear payoff:
   - reduce unnecessary nesting or branching
   - remove duplication introduced by recent edits
   - inline single-use abstractions that obscure intent
   - split code only when it creates a clearer boundary
   - improve names when they clarify purpose
   - remove comments that only repeat obvious code
3. Skip changes that are only stylistic, risky, or hard to prove behavior-preserving.
4. Apply the smallest coherent patch.
5. Run the narrowest relevant verification command. Broaden verification when shared behavior changed.
6. Report what changed and what was verified.

## Guardrails

- Do not add features, options, new dependencies, or speculative flexibility.
- Do not change error messages, serialization, ordering, timing, permissions, or external calls unless the user asked.
- Do not convert clear conditionals into nested ternaries or dense one-liners.
- Do not remove helpful abstractions just to reduce line count.
- Do not rewrite an entire module when a local simplification is enough.
- Do not claim behavior is preserved without fresh verification evidence.

## Good Targets

| Signal | Useful Simplification |
| --- | --- |
| Repeated blocks from recent edits | Extract or consolidate only the repeated intent |
| Deep `if` nesting | Use early returns or clearer branching |
| Temporary variables with unclear names | Rename to describe domain meaning |
| Single-use wrapper function | Inline it if it hides more than it helps |
| Comments narrating code | Remove or replace with a reason-oriented comment |

## Stop Conditions

Stop and ask before editing when behavior preservation depends on product intent, undocumented compatibility, or unclear external contracts. If verification cannot be run, say exactly what was not verified.
