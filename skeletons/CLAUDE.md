# CLAUDE.md

<!-- Skeleton Agent bootstrap (methodology K-002): the Binding block plus
     pointers. Keep under ~200 lines; nothing here may be authoritative —
     anything load-bearing belongs under docs/ (K-001). -->

## Methodology — binding

This project follows majodali/methodology v<VERSION> as declared in
docs/classification.md. That file strictly defines this project's
document lifecycles and workflows. Read it before any work; nothing
in this file or under .claude/ overrides it.

Classification: <C-tier> / <S-level> / <type> / <target>
Deviations: <none | one line per deviation — recorded in docs/classification.md>

## Reporting and writing — cached from W-008; do not edit here

Reports to the human owner carry three parts, in this order:

1. **Asks** — the decisions and actions requested of the reader.
2. **What is already covered** — the parts of the deliverable that
   encode decisions the conversation already settled.
3. **What changed** — the parts that are new, each with a named
   pointer into the deliverable and what to review there.

State an empty part; never drop it: "No asks", "We already covered
everything in the document", "The content is all new".

Lead with the outcome or the decision needed, never with the process
that produced it. Write short, direct sentences, one idea each. Cut
clauses that add tone but not content: dramatic accumulation,
aphorism, suspense. Name every identifier you cite.

Authority: majodali/methodology W-008 (reports map their
deliverables), the P- rules, and its style guide. This block is a
cache — amend it upstream, never here.

## What this project is

<One or two sentences.>

## Build / run / test

<Commands only; explanations live in docs/.>

## Architecture at a glance

<A few lines; the design notes in docs/ are authoritative.>

## Conventions

<Project-specific conventions, briefly.>

## Pointers

- docs/classification.md — the binding declaration
- docs/backlog.md — what is done and what is next
- docs/decisions.md — decision register (C2+)
- docs/open-risks.md — risk register (when pressure appears)
- docs/plans/ — plan documents (C2+)
