---
name: universal-problem-ledger
description: Detect, classify, deduplicate, document, update, and resolve problems raised in AI conversations. Route public-safe technical or scientific knowledge to the KenDur public GitHub ledger, ordinary non-public knowledge to the private Daybook database, and high-risk secrets to a restricted encrypted vault reference.
version: 1.0.0
---

# Universal Problem Ledger

## Purpose

Convert problems raised during normal AI use into durable, searchable knowledge without requiring the user to explicitly request documentation every time.

A **problem** includes:

- a failure, fault, defect, error, incompatibility, or unexpected behavior;
- an unresolved technical, scientific, personal, household, work, financial, health, legal, creative, or planning question;
- a decision with material tradeoffs that may need revisiting;
- a recurring annoyance, blocker, risk, or unmet need;
- an attempted solution whose outcome should be preserved;
- a lesson that would prevent repeated investigation.

Do not create records for casual remarks, rhetorical complaints, trivial one-off facts, or questions whose answers have no likely future retrieval value.

## Non-negotiable routing order

Classify before writing.

### Route 1: Public GitHub

Write to `kendur/kendur-problem-ledger` only when all of the following are true:

- the useful content is technical or scientific;
- unrestricted publication is safe;
- the source is authorized for public disclosure;
- identifying and confidential context has been removed;
- sanitization does not distort the technical facts.

Follow `docs/ROUTING_POLICY.md`.

### Route 2: Private Daybook

Write all other ordinary non-public problem knowledge to the user's private Daybook knowledge base, including personal, household, work, health, financial, legal, family, creative, project, and planning context.

Default to Daybook whenever public suitability is uncertain.

### Route 3: Restricted vault

Never store passwords, tokens, recovery codes, private keys, full financial identifiers, government identifiers, alarm codes, exploitable physical-security procedures, or prohibited confidential content in an AI-indexed knowledge base.

Store only a redacted pointer to an encrypted vault location. Never echo the secret into summaries, tags, titles, logs, issue bodies, or commit history.

## Workflow

### 1. Detect

Identify whether the conversation contains a durable problem record or a meaningful update to one.

Capture at least:

- concise title;
- summary;
- affected systems, people, projects, or domains;
- symptoms, evidence, constraints, and impact;
- actions already attempted;
- current state and next action.

### 2. Classify sensitivity

Apply the routing order above. When uncertain, choose the more private destination.

For proposed public records, perform an explicit sanitization review for:

- names and usernames;
- employers and internal organizational details;
- addresses, precise locations, schedules, and identifying dates;
- account IDs, IP addresses, MAC addresses, serial numbers, work orders, and ticket IDs;
- screenshots or logs containing private context;
- security-relevant topology or access procedures;
- proprietary parameters or unpublished designs.

### 3. Search before creating

Search the selected destination using:

- exact and normalized product or system names;
- symptom and error-text fragments;
- protocols, components, and technologies;
- likely root causes;
- aliases and common misspellings;
- related tags.

Classify the candidate as:

- `new` — no meaningful match;
- `update` — same continuing problem;
- `recurrence` — same resolved or dormant problem happened again;
- `related` — materially connected but distinct;
- `duplicate` — redundant record that should point to the canonical record.

Prefer updating a canonical record over creating near-duplicates.

### 4. Assign identifiers

For public GitHub records, use `KPL-YYYY-NNNN`.

For private Daybook records, use `DBP-YYYY-NNNN` unless the Daybook schema defines another stable prefix.

Never reuse an identifier.

### 5. Tag for retrieval

Use controlled tags covering the applicable dimensions:

- domain;
- problem type;
- symptom or effect;
- affected system or component;
- protocol or technology;
- lifecycle state;
- root cause after confirmation;
- resolution pattern after verification.

Use 5–12 high-value tags for a normal record. Put alternate wording, abbreviations, common misspellings, model names, and exact error phrases in aliases or search terms rather than creating redundant tags.

For public records, follow `docs/TAG_TAXONOMY.md`.

### 6. Capture evidence and investigation history

Preserve chronology. For each meaningful test or change, record:

- date or sequence;
- action taken;
- result observed;
- conclusion supported or rejected.

Keep rejected hypotheses. They prevent future agents from repeating failed paths.

Distinguish clearly among:

- observation;
- user report;
- measurement;
- external evidence;
- hypothesis;
- inference;
- confirmed root cause.

Do not promote an inference to root cause without sufficient evidence.

### 7. Record resolution quality

A record is not `resolved` merely because the symptom temporarily disappeared.

Resolution should include:

- root cause, or an explicit statement that it remains unknown;
- fix or intentional disposition;
- verification method;
- remaining risk;
- recurrence monitoring when appropriate;
- reusable lesson or preventive action.

Use `monitoring` when a fix exists but has not been observed long enough to verify.

### 8. Link related knowledge

Create relationships to:

- earlier occurrences;
- prerequisite configurations;
- affected systems or projects;
- public generalized technical records;
- SOPs, checklists, decisions, or reference documents created from the problem.

A private record may link to a public record. A public record must never expose or link to its private source.

### 9. Return a concise receipt

After a successful write, report:

- destination;
- record ID;
- created, updated, recurrence, related, or duplicate;
- current status;
- title;
- link when available;
- any follow-up that still needs the user.

Do not interrupt the main conversation with a long ledger dump.

## Daybook field requirements

When the private Daybook connection is available, populate these fields when supported:

- `Problem ID`
- `Title`
- `Status`
- `Record Type`
- `Sensitivity`
- `Domains`
- `Systems`
- `People`
- `Projects`
- `Tags`
- `Aliases / Search Terms`
- `Created`
- `Updated`
- `Last Seen`
- `Recurrence Count`
- `Summary`
- `Context`
- `Symptoms`
- `Impact`
- `Evidence`
- `Troubleshooting / Investigation`
- `Hypotheses`
- `Root Cause`
- `Workaround`
- `Resolution`
- `Validation`
- `Lessons`
- `Follow-up`
- `Related Records`
- `Public Technical Record`
- `Source Platform`
- `Source Reference`

Do not force empty values when the destination supports sparse properties. Preserve uncertainty explicitly.

## Suggested Daybook views

- Inbox / needs triage
- Open problems
- Waiting on user
- Monitoring
- Recently resolved
- Recurring problems
- By domain
- By system
- By project
- By person
- Work-sensitive
- Health and wellness
- Financial and legal
- Household and property
- Decisions to revisit
- Lessons worth converting to SOPs

## Failure behavior

If the selected destination is unavailable:

1. produce a complete portable record in structured Markdown or JSON;
2. mark it `pending-sync`;
3. do not silently route private content to the public repository;
4. do not claim the record was saved;
5. sync later only through an explicit connected workflow.

If classification remains uncertain, preserve the record privately or return it for private ingestion. Never gamble on public disclosure.
