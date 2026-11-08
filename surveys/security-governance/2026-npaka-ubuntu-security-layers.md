**English** | [日本語](2026-npaka-ubuntu-security-layers.ja.md)

# Ubuntu security layers: Desktop, Server, and agent isolation conditions

- This introductory article by npaka surveys Ubuntu protections, maintenance, and Desktop/Server entry paths, using 26.04 LTS as its reference.
- Actual protection depends on AppArmor profiles, Snap confinement, and whether encryption and firewall controls are active.
- It is not a defense-rate benchmark or OS ranking; ordinary-user agents still need boundaries for files, credentials, and communication.

## Practical interpretation (7 lines)

- Distinguish Desktop software/credential threats from Server exposure through services, SSH, and configuration.
- An enabled AppArmor system does not establish appropriate enforced confinement for every process.
- Check Strict, Classic, and Devmode rather than inferring safety from the Snap format.
- Separate LUKS/TPM protection at rest from information accessible after unlocking.
- Do not assume UFW alone governs Docker-published ports or agent destinations.
- Track OS maintenance, APT packages, pip/npm dependencies, and container images separately.
- The proposed inventory below was not performed; no settings, software updates, or attack experiments were run.

## Metadata and verification

- Original title: Ubuntuのセキュリティの仕組み - 標準機能と安全に使うための対策.
- Author: npaka. Published November 8, 2026 at 21:21 JST, as displayed.
- Type: personal explanatory article, not an academic paper or comparative benchmark; no DOI/arXiv ID.
- Checked: November 8, 2026 JST; current web text without a fixed version number.
- Scope: requested text read through its end; selected Canonical, Snap, and Docker documentation checked for mechanisms, 26.04 changes, maintenance, and two vulnerability examples.
- Not performed: Ubuntu device inspection, configuration changes, software updates, malware/exploit reproduction, or defense measurement.

## Question, method, and comparison conditions

What do built-in Ubuntu protections cover, and where are configuration and ongoing maintenance still needed? The article emphasizes user-executed code for Desktop and exposed services for Server, without making their threats mutually exclusive.

It is a feature-and-incident overview, not an experiment with matched attacks, settings, and hardware. This note checks selected applicability conditions and separates our agent proposals from source claims.

## Claims and supporting evidence

| Layer | Features covered | Conditions and limits |
|---|---|---|
| Boot and privileges | Secure Boot, users/groups, sudo | Boot signatures and runtime access rights differ; non-root processes can still read accessible data |
| App isolation | AppArmor, Snap | Inspect profiles, modes, and connected interfaces |
| Updates and maintenance | APT, unattended-upgrades, Ubuntu Pro | Release, component, and installation source determine coverage |
| Stored data | LUKS, TPM, credential management | Encryption selection, hardware compatibility, and unlocked state matter |
| Networking | UFW, TLS, SSH, VPN | Separate host rules, container exposure, and encrypted channels |

AppArmor policies apply to particular applications. Enforce and complain modes differ: loading a profile is not evidence that intended denials are enforced. Strict Snap confinement uses AppArmor, seccomp, namespaces, and permitted interfaces. Classic grants access closer to conventional packages; Devmode relaxes enforcement for development. Store distribution does not guarantee uniform confinement or harmless behavior.

Canonical documents UFW as initially disabled. The actual system was not inspected, and disabled UFW does not establish absence of other host/cloud filtering. Docker documents that published-port traffic can be diverted before the chains used by UFW. “UFW enabled” alone is therefore insufficient to determine container exposure.

### 26.04 LTS and maintenance

Canonical describes TPM-backed full-disk encryption as generally available for Ubuntu Desktop 26.04, subject to hardware and configuration limitations. This is not automatic coverage for every server or existing installation. sudo-rs is the default in 26.04, but the LTS transition summary dates its introduction to 25.10; it is not new for the first time in 26.04.

The official security article describes user-facing AppArmor permission prompting as experimental and disabled by default. PQC support in updated cryptographic libraries also does not mean every connection negotiates PQC.

The official lifecycle table checked on this date lists standard maintenance for 26.04 LTS through May 2031. Pro/Legacy extend scope and duration, not maintenance of every external dependency. Automatic updates depend on configured origins; pip, npm, external repositories, and container images need separate tracking.

### Incident scope checked

- **regreSSHion, CVE-2024-6387:** Canonical supplied fixes on July 1, 2024 for affected Ubuntu 22.04 LTS, 23.10, and 24.04 LTS packages. Exploitability depends on architecture and additional patches; this is not unconditional compromise of every exposed SSH service.
- **XZ, CVE-2024-3094:** Canonical lists released Ubuntu versions as unaffected. The affected package was in noble-proposed and removed before migration. This is not an incident in which all stable Ubuntu releases carried the backdoor.

## Limitations

The qualitative ratings do not rank Ubuntu, Mac, and Windows. Desktop/Server, VM/container, release/image, policy, privileges, port exposure, and maintenance coverage change the conditions.

Trusted distribution and patched operating systems do not by themselves settle what authorized code can read or whether an agent follows hostile external instructions. Non-root execution or being inside a container alone does not demonstrate adequate isolation.

## Related notes and proposed application

- [Mac security layers](2026-npaka-macos-security-layers.md) and [Windows security layers](2026-npaka-windows-security-layers.md): map protection roles and applicability across the companion articles.
- [Layered containment of autonomous agents on Kubernetes](2026-kubernetes-autonomous-agent-containment.md): compares separate controls for privileges, workspaces, and communication.

A proposed inventory records the agent's user, writable locations, secrets, host mounts, published ports, and destinations, alongside AppArmor scope and mode. Determine which boundaries are actually enforced. This is our application proposal, not measured agent-defense effectiveness from the article.

## Free verification proposal — not performed

If an Ubuntu environment is available, inspect its release, Desktop/Server and VM/container context, AppArmor profiles/modes, Snap confinement/interfaces, encryption display, UFW/exposed ports, and update origins without changing them.

Do not enable a firewall during an SSH session, disable protections, update packages, or reboot as part of this inventory. Do not include keys, tokens, recovery material, or private-file contents in reports.

- Use status: proposed only; no device verification or adoption.
- Next checks: actual process profiles, Docker/host traffic paths, and maintenance scope for dependencies.

## Sources

- Requested explanation: [npaka](https://note.com/npaka/n/nb718fa9cb373)
- Primary documentation: [26.04 security changes](https://ubuntu.com/blog/ubuntu-26-04-lts-security-updates), [LTS transition summary](https://documentation.ubuntu.com/release-notes/26.04/summary-for-lts-users/)
- Primary documentation: [AppArmor](https://ubuntu.com/server/docs/how-to/security/apparmor/), [Snap confinement](https://snapcraft.io/docs/explanation/security/snap-confinement/)
- Primary documentation: [UFW](https://ubuntu.com/server/docs/how-to/security/firewalls/), [Docker and firewalls](https://docs.docker.com/engine/network/packet-filtering-firewalls/)
- Primary documentation: [Lifecycle](https://ubuntu.com/about/release-cycle), [Pro scope](https://ubuntu.com/pricing/pro), [Security updates](https://documentation.ubuntu.com/security/security-updates/)
- Primary documentation: [regreSSHion](https://ubuntu.com/blog/ubuntu-regresshion-security-fix), [XZ impact](https://ubuntu.com/security/CVE-2024-3094)
