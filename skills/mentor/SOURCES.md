# Design sources

Design principles are taught only from these. The maintainer adds sources by
PR.

## Allowlist

**ux**
- Nielsen Norman Group — https://www.nngroup.com/articles/
- Baymard Institute — https://baymard.com/blog
- GOV.UK Service Manual — https://www.gov.uk/service-manual
- GOV.UK Design System — https://design-system.service.gov.uk/
- Steve Krug, *Don't Make Me Think* (book)
- Don Norman, *The Design of Everyday Things* (book)
- Teresa Torres, *Continuous Discovery Habits* (book)
- Steve Portigal, *Interviewing Users* (book)

**visual**
- Apple Human Interface Guidelines — https://developer.apple.com/design/human-interface-guidelines/
- Material Design 3 — https://m3.material.io/
- Adam Wathan & Steve Schoger, *Refactoring UI* (book)
- Matthew Butterick, *Practical Typography* — https://practicaltypography.com/

**both**
- W3C WAI / WCAG 2.2 — https://www.w3.org/WAI/

Books can't be fetched: explainers cite them by chapter and page, and live
fetch-and-cite uses the web sources only.

## Explainers in `docs/learn/design/`

Explainers are the reviewed cache that makes "sources, never memory" fast. A
wrong explainer is memory with a citation, so each one is gated:

```md
---
sources:
  - https://www.nngroup.com/articles/recognition-and-recall/
verified: 2026-10-20
reviewed_by: <maintainer's GitHub login>
---
```

- **Every claim** links to an allowlisted source with a short quote.
- **Reviewed** — you write it and open a PR; the maintainer sets `reviewed_by`
  when approving. Without `reviewed_by`, teach by fetch-and-cite instead.
- **Fresh** — `verified` older than 12 months → re-fetch each source, update
  the explainer if the source changed, set `verified` to today, and open a PR.

Everything else follows the [explainer rules](SKILL.md#explainers): one
concept, a real example from this codebase, two recall questions.
