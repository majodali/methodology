# Rule corpus — organization and seed extraction

The rule corpus lives in this directory, one file per section:
[knowledge.md](knowledge.md) (`K-`),
[working-agreement.md](working-agreement.md) (`W-`),
[mirrors.md](mirrors.md) (`M-`),
[prose.md](prose.md) (`P-`),
[quality.md](quality.md) (`Q-`), and
[security.md](security.md) (`S-`). The organization below was Part III of
*The Methodology Constitution & Vocabulary — Draft v0.7*; the seed notes
were the header of *Rule Corpus — Seed Extraction v0.1*. The draft
changelog is preserved as pre-1.0 history in
[constitution.md](../constitution.md#draft-history-pre-10).

## Seed extraction v0.1 — import notes

The first extraction pass (draft open item 5, now in the
[Backlog](../backlog.md)): proposal practices
A0–B6 converted into `K-` and `W-` rules, the `M-` mirrors of the
constitutional direct duties, and the two `S-` rules the Article 7 C0
baseline promised. Every rule follows the format below and carries its
motivating instance per Article 6 — for this seed, the instances are the
live repos that evolved each practice and the founding working sessions
recorded in the [proposal](../practices.md) and
[constitution](../constitution.md) drafts.

Import notes: draft-relative links become repo-relative on import; rule
first-adoption clocks (Article 6) start when a rule is first *in play*,
which for most of these is the first project migration, not this
document's creation. Tags follow Article 4/5: unstated conditions default
to `[C1+]`, all S-levels, all types, all targets; `[C0+]` tags use the
widening exception below.

## Sections

Rules are organized by discipline, mirroring the proposal, plus a meta
section. Section scopes are expressed in applicability-tag notation
([Article 4](../constitution.md#article-4--applicability-then-precedence))
— never in prose:

| Section | ID prefix | Default scope |
|---|---|---|
| Meta (constitutional machinery: amendments, audits, custom types) | `M-` | `[C1+]` |
| Knowledge & memory | `K-` | `[C1+]` |
| Working agreement | `W-` | `[C1+]` ¹ |
| Prose & presentation | `P-` | `[C1+]` ¹ |
| Quality & verification | `Q-` | `[C1+]`, narrowed per rule |
| Delivery & environments | `D-` | `[C1+] [deployable]` |
| Security & privacy | `S-` | `[S0+]` ¹ ² |
| Operations | `O-` | `[C1+] [deployed]`, narrowed per rule |

¹ Individual rules carry the C0 baseline via the widening exception:
test-modification, README, and reports (W-008) in `W-`; secret hygiene
in `S-`; supersession (K-010, K-011) in `K-`; all of `P-`. The shared
ruling (owner, 2026-08-30): these rules bind conduct and existing
content only, minting no coverage duties, so tier does not change the
burden.
² The `[S0+]` floor is deliberate: secret hygiene matters most in public
code.

*(Register entry IDs inside projects — decision D-numbers etc. — are a
separate namespace from rule IDs; rule IDs are letter-prefixed per this
table and unique across the corpus.)*

## Rule ID and header format

```
### Q-004 — Functional tests run against a deployed test environment
Applies: [C2+] [type: web-app, backend-service]
Keywords: MUST
Motivated-by: [in-real-life CI pipeline](…)
Cites: —
```

The body follows with labeled fields — **Statement** (the norm),
**Rationale** (why, optional), **Exceptions** (bounded carve-outs, if
any) — per the [style guide](../style.md). Rules predating the labels
migrate editorially. Applicability tags use
Classification fields and vocabulary-defined derived conditions only, so
applicability is mechanically decidable from the Article 4 basis — the
Classification together with the designations it references.

## Section applicability marking

A section or subsection MAY carry an `Applies:` header inherited by its
rules. Rule-level tags narrow inherited scope, with one defined widening
exception: a rule MAY lower the inherited minimum C-tier **to `[C0+]`
only** — no intermediate lowering (a `[C2+]` section cannot host a
`[C1+]` rule; such a rule belongs in a section whose scope fits). The
exception exists solely so sections can carry the C0 baseline (as W- and
S- do). No other widening is permitted, keeping precedence computable.

## Constitutional mirrors

Obligations the Constitution attaches to specific projects or processes —
the amendment-PR traceability review (Article 8), the review-round
methodology audit and census (Article 9), Portfolio-register completeness
(Article 9) — are each mirrored as an `M-` rule citing its constitutional
source, so the rule-driven audit tooling verifies them like everything
else. Mirrors binding the methodology repo alone tag
`[type: methodology-corpus]`, the reserved singleton. The Constitution
remains authoritative; the mirror is machinery.

## Extraction notes for the first review round

- **Coverage**: A0–A8 → K-001–K-009 (A6 folded into K-001 rather than
  minted separately — no distinct force); B1–B6 → W-001–W-006; the C0
  baseline promises of Article 7 →
  [W-002](working-agreement.md#w-002--existing-tests-are-signals-not-obstacles),
  [W-007](working-agreement.md#w-007--every-project-has-a-readme-that-says-what-it-is),
  [S-001](security.md#s-001--no-secrets-in-repositories-ever)/[S-002](security.md#s-002--exposure-means-rotate-and-purge-immediately);
  the three
  constitutional direct duties → M-001–M-003. The C-, D-, O-, Q-
  disciplines and remaining S- rules await their own extraction passes,
  each with live motivating instances (Q-004's header example above is a
  preview, not yet a rule).
- **Article 7 placeholders**: now resolved — B2 →
  [W-002](working-agreement.md#w-002--existing-tests-are-signals-not-obstacles),
  README →
  [W-007](working-agreement.md#w-007--every-project-has-a-readme-that-says-what-it-is),
  secret hygiene →
  [S-001](security.md#s-001--no-secrets-in-repositories-ever)/[S-002](security.md#s-002--exposure-means-rotate-and-purge-immediately).
- **First-adoption clocks**: none of these rules is in play until a
  project pins a version containing them (or an unpinned C0 repo exists
  for the `[C0+]` rules — which the Portfolio census will enumerate).
- **Known tensions to attack in review**: K-003's stage-designation
  clause restates part of Article 4's accuracy duty (mirror or
  duplication?); W-001's "larger arcs" threshold is undefined and may
  need a vocabulary term or owner judgment marker; M-003's subject is
  arguably the *process* rather than the repo — the tag language may
  want a process-scoped notion eventually.
