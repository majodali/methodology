# M — Constitutional mirrors

Seed extraction v0.1 — see the [rule corpus organization and import
notes](README.md), including the
[constitutional-mirrors section](README.md#constitutional-mirrors): the
Constitution remains authoritative; the mirror is machinery.

### M-001 — The Portfolio register is complete
Applies: [type: methodology-corpus]
Keywords: MUST
Motivated-by: [Constitution Article 9](../constitution.md#article-9--audits) (mirror; the Constitution is authoritative)
Cites: —

The Portfolio register MUST contain every majodali project, including
implicit-C0 repositories. Entries carry name, location, and an
informative classification summary; each project's own Classification
remains authoritative. Completeness is verified by the census pass
([M-002](#m-002--the-review-round-audit-and-census-run)).

### M-002 — The review-round audit and census run
Applies: [type: methodology-corpus]
Keywords: MUST
Motivated-by: [Constitution Article 9](../constitution.md#article-9--audits) (mirror)
Cites: —

A semantic audit of the methodology MUST run at every review round,
whatever its declared tier. It MUST sweep the Portfolio register and
include the census pass: reconciling the register against observable
repositories (refreshing stale summaries) and spot-checking declarations
— including implicit-C0 defaults — against observable state. It MUST
execute Article 6 anti-languish flagging and examine corpus defects and
convergent custom definitions.

### M-003 — Amendment PRs receive traceability review
Applies: [type: methodology-corpus]
Keywords: MUST
Motivated-by: [Constitution Article 8](../constitution.md#article-8--amendments-versions-and-migration) (mirror)
Cites: —

Every amendment PR MUST receive the traceability-link review of Article
9 regardless of the methodology's declared tier: reviewers follow the
evidencing-instance link and verify the change against the current
standard and all open proposals.

### M-004 — Amendment PRs carry their release-register entry
Applies: [type: methodology-corpus]
Keywords: MUST
Motivated-by: [release process](../release-process.md) (mirror; that document is authoritative); the audit-log amendment ([PR #3](https://github.com/majodali/methodology/pull/3)), whose adjudication surfaced the missing provenance/impact/migration record
Cites: [Keep a Changelog](https://keepachangelog.com/) (register shape)

Every amendment PR MUST include, in the same diff as the change, its
entry in the [Release register](../releases.md)'s Unreleased section:
amendment title and PR link, suggested by (evidencing instance), impact
assessment covering every affected Portfolio project, and an explicit
migration note (`none` stated, never omitted). A proposal without its
entry is not adjudicable; rejection removes the entry with the closed
PR. (This rule mirrors the release process, a Methodology-level
document under Article 8, the way M-001–M-003 mirror the Constitution —
the M- section is Meta machinery, not constitutional mirrors alone.)
