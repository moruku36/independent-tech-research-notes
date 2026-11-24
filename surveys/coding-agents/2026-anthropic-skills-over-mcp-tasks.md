**English** | [日本語](2026-anthropic-skills-over-mcp-tasks.ja.md)

# Claude’s MCP update: skills, background tasks, and user input

## Overview

- **What it is**: An Anthropic release announcement on Skills over MCP, Tasks, Elicitation, and File Uploads in Claude and Claude Code.
- **What it says**: MCP servers can publish contextual guidance, run asynchronous work, or request user input. File transfers were announced for later rollout.
- **Caveat**: Availability differs by feature, plan and administrator settings. An optional extension also needs compatible endpoints.

## Practical reading (six lines)

- Skills over MCP lets a connected server publish instructions alongside its tools. Claude can load them when a task needs them.
- At launch it was in public beta, enabled by default on Pro, Max and Ultra, with admin opt-in for Team and Enterprise support planned.
- Tasks lets the server run work asynchronously. Elicitation lets it ask for input during a call.
- Tasks and Elicitation were generally available on Pro, Max and Ultra, with Team and Enterprise rollout underway.
- File Uploads was announced for later rollout. Transferring a file outside the model context still sends it to the destination service.
- Proposed use: check each connector’s supported features, consent prompt, allowed actions, task state and file destination before enabling it.

## Source and reading scope

Anthropic, November 24, 2026. Checked the official announcement and selected MCP extension references on November 25, 2026 JST. Plans and availability refer to the announcement. No connector, workflow or file transfer was run.

## Evidence and limitations

- **Product stages.** Skills over MCP is a public beta. Tasks and Elicitation have a different rollout schedule. File Uploads is listed as coming soon for Pro, Max, Ultra and eligible Team and Enterprise plans. Compatibility depends on the client and the server negotiating the applicable capabilities.
- **Trust and controls.** The MCP Skills beta specification treats server-served text as untrusted model input. File hashes can bind approval to the reviewed resource set and detect changes relative to it. They do not prove the publisher or instructions are trustworthy. Scope tool authorization separately from the skill and retain user approval for consequential actions.
- **Asynchrony and files.** Tasks defines status and result retrieval for background work. The product’s Elicitation examples use user input in the middle of a task. File handling still needs a clear destination and retention policy even when transferred bytes stay out of model context.

## Application and free check

Proposed. Use a mock connector with a read-only task and a fictional file. Record where instructions came from, what changes would require fresh review, how a pending task is tracked, and when the user is asked before an action or transfer.

## Related notes

- [Typed agent capabilities](2026-skillware-typed-agent-capabilities.md)
- [MCP control ownership](../security-governance/2026-mcp-security-three-tier-mitigation.md)

## Sources

- [Requested Japanese announcement](https://claude.com/ja/resources/articles/skills-over-mcp-tasks-and-more)
- [English announcement](https://claude.com/resources/articles/skills-over-mcp-tasks-and-more)
- [MCP Skills extension](https://skills.extensions.modelcontextprotocol.io/specification/beta/skills)
- [MCP Tasks extension](https://tasks.extensions.modelcontextprotocol.io/specification/2026-07-28/tasks)
- [MCP File Uploads proposal](https://blog.modelcontextprotocol.io/posts/exploring-file-uploads-and-downloads-in-mcp/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
