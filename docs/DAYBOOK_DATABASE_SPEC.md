# Private Daybook Problem Ledger Specification

This document defines the private destination used by the Universal Problem Ledger. It contains schema guidance only; no private records belong in this public repository.

## Recommended structure

Create a dedicated Notion database named **Private Problem Ledger** under the user's Daybook area. Do not use one giant free-form Daybook page as the canonical store.

Embed linked views of the database in Daybook so the Daybook remains the navigation surface while the dedicated database provides stable properties, filtering, relations, and deduplication.

## Core properties

| Property | Notion type | Purpose |
|---|---|---|
| Problem | Title | Human-readable record title |
| Problem ID | Unique ID or text | Stable identifier such as `DBP-2026-0001` |
| Status | Status | Inbox, triage, investigating, blocked, waiting, monitoring, resolved, archived |
| Record Type | Select | Incident, question, decision, risk, recurring problem, unmet need, experiment, follow-up |
| Sensitivity | Select | Private, confidential, restricted-reference |
| Severity | Select | Informational, low, medium, high, critical |
| Domains | Multi-select | Broad retrieval categories |
| Tags | Relation | Relation to the controlled Tag Registry |
| Search Terms | Rich text | Aliases, abbreviations, errors, misspellings, and natural-language phrases |
| Systems | Rich text or relation | Devices, software, processes, assets, services, or equipment |
| Projects | Relation | Related projects when a project database exists |
| People | Relation or people | People materially involved; avoid unnecessary names |
| Created | Created time | First capture timestamp |
| Updated | Last edited time | Last meaningful update |
| Last Seen | Date | Latest occurrence |
| Recurrence Count | Number | Number of known occurrences |
| Summary | Rich text | Standalone concise description |
| Impact | Rich text | Consequence, scope, urgency, and frequency |
| Root Cause | Rich text | Confirmed cause or explicit unknown |
| Current State | Rich text | Best current understanding |
| Next Action | Rich text | Immediate next step |
| Follow-up Date | Date | Review or action date |
| Resolution | Rich text | Final fix, disposition, or decision |
| Validation | Rich text | How the outcome was verified |
| Public Record | URL | Optional sanitized GitHub counterpart |
| Vault Reference | Rich text | Redacted pointer only; never the secret itself |
| Source Platform | Select | ChatGPT, Claude, Gemini, Codex, local agent, email, meeting, manual |
| Source Reference | URL or rich text | Conversation, document, message, or external reference |
| Related Problems | Relation | Self-relation to connected records |
| Duplicate Of | Relation | Canonical-record pointer |

## Page body template

Keep long-form and chronological material in the page body:

1. Summary
2. Context
3. Expected and actual state
4. Symptoms and impact
5. Constraints
6. Evidence
7. Hypotheses
8. Investigation log
9. Root cause
10. Workaround
11. Resolution
12. Validation
13. Lessons
14. Follow-up
15. Related records

## Controlled Tag Registry

Create a second database named **Problem Tag Registry** rather than allowing uncontrolled multi-select sprawl.

Recommended properties:

| Property | Type | Purpose |
|---|---|---|
| Tag | Title | Canonical lowercase hyphenated tag |
| Tag Type | Select | Domain, topic, system, person-role, symptom, problem-type, cause, resolution, lifecycle, context |
| Description | Rich text | Precise meaning and inclusion rule |
| Aliases | Rich text | Alternate language, abbreviations, misspellings |
| Parent Tag | Relation | Optional hierarchy |
| Merge Into | Relation | Canonical replacement for duplicates |
| Active | Checkbox | Prevent use of deprecated tags |
| Usage Count | Rollup | Number of related problem records |

### Suggested private domains

- `work`
- `career`
- `household`
- `property`
- `family`
- `relationship`
- `health`
- `finance`
- `legal`
- `housing`
- `vehicle`
- `pet`
- `creative`
- `project`
- `purchase`
- `travel`
- `schedule`
- `communication`
- `decision`
- `security`
- `personal-technology`

Use additional technical tags from `docs/TAG_TAXONOMY.md` where applicable.

## Recommended views

- **Inbox** — status is Inbox or Triage
- **Needs action** — unresolved with a next action
- **Waiting on me** — user input or decision required
- **Waiting on others** — blocked by another person or organization
- **Monitoring** — fix or decision made but not yet validated
- **Recurring** — recurrence count greater than one
- **Recently updated** — descending by Updated
- **Recently resolved** — resolved within the last 30 days
- **By domain** — grouped by Domains
- **By system** — grouped or filtered by affected system
- **By project** — grouped by Project relation
- **Sensitive work** — domain includes Work and sensitivity is Confidential
- **Health / financial / legal** — filtered private review views
- **Convert to SOP** — resolved records with reusable lessons
- **Decision review** — decisions whose follow-up date is due

## Search and deduplication strategy

Before creating a record, search in this order:

1. exact Problem ID;
2. title and close semantic variants;
3. Systems;
4. Search Terms and exact error text;
5. Tags;
6. related project or person;
7. root cause and resolution language.

Use one canonical record and increment `Recurrence Count` rather than creating a new page for every recurrence. Preserve each occurrence in the investigation log with date, context, and outcome.

## Security boundary

The private Daybook database is appropriate for ordinary non-public information, but it is not a credential vault. Store secrets and high-risk identifiers in encrypted secret storage and place only a redacted vault reference in Daybook.

Employer-confidential content must also comply with the employer's approved storage and AI-processing policies. When authorization is absent or unclear, retain only a sanitized personal action summary rather than proprietary source material.
