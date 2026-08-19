# majodali/methodology

The standard development methodology for majodali projects: a
Constitution, a shared vocabulary, and a rule corpus written in that
vocabulary, governing the process and documentation aspects of every
project in the portfolio.

This corpus holds norms and the vocabulary they are written in; technique
knowledge lives in the handbook (future sibling repo) and is cited, never
inlined.

## Layout

- [docs/constitution.md](docs/constitution.md) — Level 1 of exactly
  three: governs the methodology itself; changes rarely, by human
  decision only.
- [docs/vocabulary.md](docs/vocabulary.md) — the standard vocabulary the
  rules are written in: classification scales, artifact and content
  types, designations, relationships, roles.
- [docs/rules/](docs/rules/README.md) — the rule corpus (seeded:
  `K-` knowledge & memory, `W-` working agreement, `M-` constitutional
  mirrors, `S-` security & privacy).
- [docs/practices.md](docs/practices.md) — the imported practice
  definitions (A0–F5) that rules cite as motivating instances; source for
  the remaining extraction passes.
- [docs/classification.md](docs/classification.md) — this repo's own
  binding Classification (the methodology is a project under its own
  Constitution).
- [docs/registers/portfolio.md](docs/registers/portfolio.md) — the
  Portfolio register: every majodali project, enumerated.
- [docs/backlog.md](docs/backlog.md) — what is done and what is next.
- [docs/open-risks.md](docs/open-risks.md) — Risk register, including
  the transitional entries of Constitution Article 11.
- [skeletons/](skeletons/) — copyable starting files for adopting
  projects.

Projects adopt the methodology by declaring a Classification
(`docs/classification.md`) that pins a methodology version, and by adding
the Binding block to their `CLAUDE.md` — see the
[skeletons](skeletons/) and the
[Classification definition](docs/vocabulary.md#artifact-types).
