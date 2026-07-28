# Routing Policy

The Universal Problem Ledger classifies every candidate record **before** writing it anywhere.

## Destination A — Public GitHub

Route to `kendur/kendur-problem-ledger` only when the record is neutral, technical or scientific, and safe for unrestricted public disclosure.

Allowed examples:

- Generic hardware, software, networking, electronics, fabrication, and automation problems
- Sanitized consumer-device troubleshooting
- Publicly reproducible experiments and benchmarks
- Open-source project defects, compatibility findings, and configuration guidance
- General scientific questions and evidence-based conclusions

## Destination B — Private Daybook

Route all non-public but ordinary personal knowledge to the private Daybook knowledge base.

Examples:

- Personal plans, purchases, household projects, family context, schedules, and correspondence
- Work notes and incidents that are not authorized for public disclosure
- Health, legal, financial, housing, career, and relationship matters
- Private creative work, unpublished designs, business concepts, and project plans
- Problems that become identifying when combined with dates, names, locations, or source material

Daybook records should remain structured, tagged, searchable, and linked to related entries.

## Destination C — Restricted vault

Do **not** write high-risk secrets into either the public repository or an AI-indexed Daybook database.

Restricted examples:

- Passwords, recovery codes, API tokens, private keys, certificates, and session cookies
- Social Security numbers, full payment-card numbers, bank-account numbers, or tax identifiers
- Alarm codes, door codes, exact physical access procedures, or exploitable security details
- Unredacted medical record identifiers or identity-document images
- Confidential files whose governing policy prohibits third-party AI processing

Store the secret itself in an encrypted password manager or encrypted private storage. The Problem Ledger may store only a redacted reference such as:

```text
Credential stored in vault: Home/Network/OPNsense Admin
```

## Public-safety decision test

A record may enter the public repository only when all answers below are **yes**:

1. Would unrestricted publication create no meaningful privacy, employment, legal, financial, physical-security, or reputational risk?
2. Has all identifying information been removed or generalized?
3. Is the source material authorized for public disclosure?
4. Does the remaining record still provide useful technical or scientific knowledge?
5. Has the agent checked for indirect identification through combinations of dates, locations, equipment names, account names, or screenshots?

If any answer is no or uncertain, route the record to private Daybook or the restricted vault.

## Sanitization rules

Before a public write, remove or generalize:

- People, employers, departments, internal system names, addresses, and exact locations
- Serial numbers, MAC addresses, IP addresses, account IDs, work-order IDs, and ticket numbers
- Screenshots containing names, notifications, coordinates, or private browser content
- Internal production data, staffing details, proprietary process parameters, and unpublished drawings
- Exact dates when they could identify a private incident; retain dates only when technically relevant and safe

Sanitization must preserve technical truth. Do not invent substitute facts. Use broad descriptors such as `consumer router`, `industrial controller`, or `Midwestern residence` only when the generalization remains technically valid.

## Conflict rule

When public GitHub and private Daybook records overlap:

- The public record contains only the generalized technical lesson.
- The private record may link to the public record and retain the private context.
- The public record must never link back to the private record.

## Default rule

When classification is ambiguous, default to **private Daybook**. Public disclosure requires positive confidence, not mere absence of an obvious secret.
