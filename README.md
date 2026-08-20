## Himanshu Srivastava

**Data and platform engineering — Dallas, TX**

I build AI into regulated workflows, and the controls that make its output
checkable. Mortgage lending mostly: loan origination systems, Ginnie Mae pool
delivery, GL reconciliation, and the CI/CD security gates around them.

The through-line in everything below is the same idea — **an automated system
should be able to prove what it did.** Not assert it. Prove it, to someone who
does not trust it.

---

### [Custody](https://github.com/Himansh97/custody) · `pip install custody-ledger`

A signed, append-only ledger for AI decisions in mortgage lending, built against
Fannie Mae Lender Letter LL-2026-04.

Two halves that are useless apart. A **deterministic gate** runs before an AI
output reaches a loan file: every figure must appear in a source document, every
field must cite one, classifications must land in a closed set, and anything under
the confidence floor goes to a person. There is no model anywhere in the
verification path — a model judging a model is not evidence. Then a **hash-chained,
Ed25519-signed ledger** records what the model produced and what a human did about
it, so the safeguard can be shown to have run rather than claimed.

- Published on [PyPI](https://pypi.org/project/custody-ledger/), v0.6.0
- 103 assertions across 12 test files; SQLite and Postgres, both tested in CI
- Ed25519 and ECDSA-P256, with keys in Azure Key Vault rather than on disk
- One runtime dependency, because this sits in the call path of a regulated workflow
- `verify_packet.py` — a single stdlib-only file so an examiner can check the
  evidence without trusting this package
- The [compliance mapping](https://github.com/Himansh97/custody/blob/main/docs/ll-2026-04.md)
  says "no" more often than a vendor document would

**[Live demo](https://himansh97.github.io/custody.html)** — the page recomputes
every hash in your own browser. Press *Tamper* and the chain breaks at the record
that was edited.

---

### CareerOS — [api](https://github.com/Himansh97/careeros-api) · [web](https://github.com/Himansh97/careeros-web)

A job search run as an engineering system. FastAPI backend, Next.js 16 frontend.

Fit scoring is deterministic and evidence-based: **no resume claim can exist
without a verified source behind it**, and a requirement the system does not
recognise is reported as a gap, never assumed as a pass. That second rule came
from a real failure — a mortgage compliance posting once scored 98/100 with "no
gaps" because the requirements it did not understand were invisible rather than
unmet.

Nothing auto-submits. The API prepares and stops; the browser automation is
structurally incapable of pressing submit. That is not caution for its own sake —
it is what the ATS terms of service actually require.

- 120 commits, 63 endpoints, 26 test files
- Containment: generated prose is discarded whole if any sentence introduces a
  figure, a proper noun or a seniority claim its source does not support

---

### [Portfolio](https://himansh97.github.io)

Live, interactive, no build step. Includes the containment gate and the Custody
ledger running in the page.

---

### Currently

AI Engineer Intern at a regulated mortgage lender, working on LOS integrations,
Ginnie Mae delivery, and AI-assisted reconciliation. MS Business Analytics and an
MBA. Lean Six Sigma Green Belt.

**Python · SQL · FastAPI · React/TypeScript · Azure (Bicep, Container Apps, Key
Vault) · GitHub Actions · Power BI · Tableau · PySpark · Airflow · Claude API ·
MISMO/ULDD · Encompass**

[hsrivast22@gmail.com](mailto:hsrivast22@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/himanshu-data-engineer/) ·
[himansh97.github.io](https://himansh97.github.io)
