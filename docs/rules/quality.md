# Q — Quality & verification

Opened by amendment (v1.3.0 candidate) with the template rule; the
remaining Q- extraction from [practices.md](../practices.md) §2.C is a
Backlog item, each rule awaiting its live motivating instance
(Article 6). See the [rule corpus organization](README.md).

### Q-001 — Template scaffolds stay compliant
Applies: [C1+] [type: template]
Keywords: MUST
Motivated-by: [serverless-web-app-template](https://github.com/majodali/serverless-web-app-template) — the reference implementation whose gaps ([practices §5](../practices.md)) showed derived projects start non-compliant unless the template ships compliance; verification instrument: `mtool classify`'s empty-to-form-clean gate, generalized
Cites: —

A template project MUST keep its shipped scaffold compliant:
instantiating the scaffold MUST produce a project that passes a form
audit at the C-tier the template declares for its derivatives (declared
in the template's own documentation, alongside any deviations a fresh
derivative is expected to record). The check runs at every template
release and in the template's own audits. A template whose scaffold
audits dirty is itself non-compliant — the burden of shipping
starting-states is that the starting-states inherit the standard.
