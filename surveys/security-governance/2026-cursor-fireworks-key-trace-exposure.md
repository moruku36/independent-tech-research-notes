**English** | [日本語](2026-cursor-fireworks-key-trace-exposure.ja.md)

# Cursor incident: vendor access, agent traces and extension distribution

## Overview

- **What it is** Incident reporting on a vendor-held key and exposed historical agent traces.
- **What it says** Cursor describes credentials in copied traces enabling further access and a malicious extension in its marketplace cache.
- **Caveat** The news body could not be fetched; the account below relies on provider disclosures, not independent forensics.

## Practical reading (six lines)

- Cursor says a key issued to Fireworks exposed a read-only shared bucket.
- Historical non-Privacy Mode traces contained some unredacted credentials.
- Those credentials enabled access to selected internal SaaS tools and data.
- A later stolen credential enabled tampering with Cursor’s extension-serving cache.
- At most 5,000 users potentially received the build over about 11 hours; this is not a confirmed infection count.
- Proposed application: minimize shared trace retention, redact secrets and separate training-data access from release credentials.

## Source and reading scope

The Hacker News, 2026-11-15, headline and opening excerpt checked through its category search results. Direct and mobile article fetches failed. Checked 2026-11-15 JST against Cursor Team, An update on our recent security incident (2026-11-13), and selected Fireworks bulletin passages updated 2026-11-09. No malware execution or independent incident investigation.

## Evidence and limitations

Cursor identifies October 29 distribution of tampered Anthropic.claude-code versions 2.1.312/2.1.313 and says Open VSX was unaffected. It reports its official app/update system and Privacy Mode prompts/code were outside this exposure. Those scope claims and containment status are provider statements. Fireworks describes broader impacts on a limited account set; its bulletin does not independently identify the particular Cursor-issued key. The incident linkage rests on Cursor’s account.

## Related notes

- [Agent approvals and secret leakage](2026-apiiro-agent-approval-secret-leaks.md)
- [KV-cache exposure](2026-cloudflare-kv-cache-exposure.md)

## Free check and usage status

Proposed, untried. Create a free offline data-flow map using fake credentials: trace capture, redaction, storage sharing, downstream SaaS and artifact distribution. Check whether a read-only dataset could still carry reusable authority and where short-lived, resource-scoped access would break the chain. Record retention, owners and revocation paths. Next inspect provider notices and independent evidence before incident-specific action; no keys were scanned or rotated and no extensions were installed.

## Sources

- [Submitted news URL](https://thehackernews.com/2026/11/stolen-fireworks-ai-key-led-to-cursor.html)
- [News category excerpt](https://thehackernews.com/search/label/Supply%20Chain/)
- [Cursor incident update](https://cursor.com/blog/security-incident-update)
- [Fireworks bulletin](https://fireworks.ai/security/bulletins/october-2026-security-incident-update)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
