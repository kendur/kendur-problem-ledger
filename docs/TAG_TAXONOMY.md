# Tag Taxonomy

Tags are lowercase, hyphenated, singular where practical, and selected from several independent dimensions. A good record normally has **5–12 tags**, not dozens of near-synonyms.

## Required tag dimensions

Every record should include at least one tag from each applicable dimension.

### Domain

- `hardware`
- `software`
- `networking`
- `linux`
- `windows`
- `android`
- `automation`
- `home-assistant`
- `self-hosting`
- `container`
- `electronics`
- `electrical`
- `mechanical`
- `fabrication`
- `audio`
- `video`
- `gaming`
- `data`
- `ai-ml`
- `science`

### Problem type

- `failure`
- `intermittent`
- `performance`
- `compatibility`
- `configuration`
- `installation`
- `integration`
- `connectivity`
- `data-quality`
- `measurement`
- `design-decision`
- `unexpected-behavior`
- `recurring`

### Symptom or effect

Examples:

- `not-detected`
- `disconnect`
- `timeout`
- `crash`
- `no-audio`
- `high-latency`
- `packet-loss`
- `overheating`
- `power-loss`
- `incorrect-reading`
- `duplicate-event`
- `slow-response`
- `permission-error`

### Component or protocol

Examples:

- `bluetooth`
- `wifi`
- `ethernet`
- `usb`
- `hdmi`
- `docker`
- `mqtt`
- `zigbee`
- `zwave`
- `matter`
- `thread`
- `api`
- `webhook`
- `database`
- `sensor`
- `firmware`

### Lifecycle

- `needs-reproduction`
- `needs-logs`
- `workaround-available`
- `root-cause-confirmed`
- `fix-verified`
- `monitoring`
- `regression`
- `upstream-bug`
- `documentation-gap`

## Product and system tags

Use normalized product or project tags when they materially improve retrieval:

- `steam-deck`
- `steamos`
- `sonos`
- `opnsense`
- `qnap`
- `proxmox`
- `nextcloud`
- `n8n`
- `ollama`
- `open-webui`
- `qdrant`
- `ragflow`
- `esphome`
- `wled`

Do not create separate tags for capitalization, model punctuation, or trivial variants. Put exact model numbers in the `systems` or `environment` fields.

## Alias and search-term rules

Tags represent controlled concepts. Put alternate wording, common misspellings, abbreviations, former product names, error text, and user language in `aliases`.

Example:

```yaml
tags:
  - audio
  - bluetooth
  - connectivity
  - not-detected
  - steam-deck
  - sonos
aliases:
  - SteamDeck
  - Move 2 missing from Bluetooth list
  - unreadable Bluetooth device names
  - BlueZ friendly name
```

## Avoid

- Personal names or usernames
- Exact addresses, IP addresses, MAC addresses, account IDs, or serial numbers
- Vague tags such as `problem`, `issue`, `help`, or `misc`
- Duplicate singular/plural tags
- Tagging every incidental technology mentioned in a discussion

## Retrieval principle

A future agent should be able to find a record using any of these paths:

1. affected system or product;
2. visible symptom or error text;
3. underlying protocol or component;
4. type of failure;
5. confirmed root cause;
6. resolution or workaround.
