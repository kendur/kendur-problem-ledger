# KenDur Problem Ledger

A public, AI-readable knowledge base for **neutral technical and scientific problems**: symptoms, investigation history, evidence, root causes, fixes, validation, and reusable lessons.

This repository is the public destination used by the **Universal Problem Ledger** skill. It is intentionally restricted to information that is safe to publish.

## What belongs here

- Computer hardware, software, networking, Linux, self-hosting, and automation
- Home Assistant, ESPHome, WLED, containers, APIs, and integrations
- Consumer-device troubleshooting with identifying details removed
- General engineering, electronics, fabrication, and scientific questions
- Reproducible experiments, benchmarks, configurations, and repair procedures
- Public project defects and technical design decisions

## What does not belong here

- Names, addresses, phone numbers, account identifiers, or other personal data
- Employer-confidential information, proprietary equipment details, or internal incidents
- Health, finances, legal matters, family matters, private correspondence, or schedules
- Home-security layouts, access methods, alarm details, credentials, tokens, or private keys
- Private creative canon, unpublished business ideas, or confidential project plans
- Anything copied from a private source unless it has been deliberately sanitized

See [`docs/ROUTING_POLICY.md`](docs/ROUTING_POLICY.md) for the complete routing rules.

## Repository layout

```text
.github/ISSUE_TEMPLATE/   GitHub intake form
problems/                 Canonical resolved and in-progress records
schemas/                  Machine-readable validation schemas
skills/                   Cross-platform AI skill instructions
templates/                Human- and agent-readable templates
docs/                     Governance and routing policies
```

## Record lifecycle

1. Detect a concrete problem, failure, unresolved question, or recurring technical issue.
2. Search existing records and GitHub Issues for duplicates or related cases.
3. Sanitize the proposed record under the routing policy.
4. Create or update an Issue while investigation is active.
5. Maintain a canonical Markdown record under `problems/`.
6. Record tests, rejected hypotheses, root cause, resolution, and validation.
7. Close the Issue only when the outcome or intentional disposition is documented.

## Stable identifiers

Use identifiers in the form:

```text
KPL-YYYY-NNNN
```

Example: `KPL-2026-0001`.

## Status values

- `triage`
- `investigating`
- `blocked`
- `monitoring`
- `resolved`
- `not-reproduced`
- `not-planned`

## Source of truth

For public-safe technical and scientific records, the Markdown file in this repository is canonical. GitHub Issues are the active work queue and discussion history.

Private or sensitive problems must be routed elsewhere and represented here only by fully sanitized, generally useful technical knowledge when appropriate.
