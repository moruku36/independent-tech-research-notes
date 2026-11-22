**English** | [日本語](2026-nebusec-meta-muse-isolation-credential-risk.ja.md)

# Meta Muse: agent isolation, private data, and credential storage

## Overview

- **What it is**: NebuSec’s security research report on the separation between Meta Muse’s execution environment and private user resources.
- **What it says**: In its demonstration, NebuSec reports access to and modification of conversation history and stored memories, and access to credential storage within the tested user VM.
- **Caveat**: The evidence concerns a research demonstration in one user environment. Affected versions, customer impact and the scope of remediation remain unconfirmed in the sources checked.

## Practical reading (six lines)

- A browser-enabled assistant processes untrusted web content alongside tasks that involve private data.
- Meta describes a per-user VM, a separate network approval component called Sentinel, and protected credential storage.
- NebuSec reports that its demonstration reached conversation history and stored memories without a network approval prompt. It also reports that it could change these records.
- The researchers report access to protected storage within the tested VM. Host and other tenant environments were outside the demonstrated scope.
- NebuSec says it notified the Muse team and that the issues it demonstrated had been patched by publication. The materials checked provide no independent confirmation of rollout or customer impact.
- Proposed use: give the browser, approval service and credential store separate privileges, then check their behavior with synthetic data when one component is assumed untrusted.

## Source and reading scope

NebuSec, November 20, 2026. Checked the public overview, its scope and remediation statements, and Meta’s product descriptions on November 23, 2026 JST. Meta’s product descriptions establish the stated control design. The demonstration and patch status are attributed to NebuSec. No account, live service, or proof of concept was tested.

## Evidence and defensive implications

- **Confidentiality and integrity.** The absence of an approval prompt did not prevent disclosure in the reported test. Being able to change persistent state raises a separate concern for later sessions. Reviews should treat conversation and memory read and write access as separate permissions.
- **Independence of controls.** Credential storage outside the ordinary agent runtime can protect data during normal execution. This case asks what happens when the runtime’s isolation assumptions fail. Bound access to secrets and authorization decisions outside the component that processes untrusted content. Design privileged access to expire, and make approval and denial events reviewable.
- **Scope of evidence.** NebuSec reports reaching the storage boundary, which alone does not establish downstream account use. Its demonstration stayed within a single user’s VM. Public materials checked do not establish patch rollout by version, the number of affected users, or evidence of exploitation outside the reported test.

## Application and free check

Proposed. Use a mock architecture with a fictional conversation, a fake credential, and an approval log. Review a small table of allowed reads, writes, and outbound actions. Assuming one component cannot be trusted, verify on paper that sensitive operations remain denied and that the approval decision and alert would be independently logged.

## Related notes

- [Structural testing for agent workflows](2026-agent-workflow-structural-testing.md)
- [Sakana AI’s Security Research Group](../security-governance/2026-sakana-ai-security-research-group.md)

## Sources

- [NebuSec’s public overview](https://nebusec.ai/research/meta-muse-credential-exposure/)
- [Meta’s description of Muse’s design](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
