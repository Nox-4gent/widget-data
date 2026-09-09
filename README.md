# widget-data

Public, generated status data for lightweight widgets and dashboards.

## Purpose

This repository is a **static data publication surface**, not an application source repository and not a private operational database. Files here may be consumed through GitHub Pages or raw GitHub URLs by simple widgets that cannot access the private control plane directly.

Current published payload:

- `opencode_status.json` — timestamped profile availability, aggregate usage counters, quota-window metadata, and basic plan/source labels.

Consumers must treat the payload's `time` field as authoritative for freshness. Data can be stale if the upstream publisher has stopped updating.

## Public-data boundary

Everything committed here must be considered public. Allowed content is limited to deliberately sanitized, low-sensitivity status/usage data required by the widget.

Never publish:

- API keys, OAuth tokens, cookies, credentials, session material, or private URLs;
- account IDs, email addresses, billing identifiers, or exact private financial/account data;
- raw logs, prompts, conversations, databases, filesystem paths, or device secrets;
- infrastructure secrets or anything required to access Hermes, Codex, Claude, Cloudflare, SSH, or local machines.

Profile labels and all numeric usage fields present in the JSON are public once committed here. If a field should not be public, remove it at the publisher before committing rather than relying on this README as protection.

## Repository shape

Keep this repository intentionally small:

```text
.nojekyll
README.md
index.html
opencode_status.json
```

Do not add application source code, build artifacts, logs, backups, or unrelated project files.
