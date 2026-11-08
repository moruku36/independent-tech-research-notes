**English** | [日本語](2026-npaka-windows-security-layers.ja.md)

# Windows security layers, applicability, and agent permissions

- This explanatory article by npaka surveys Windows 11 protections for boot, the kernel, apps, stored data, and networks.
- Defender, SmartScreen, Smart App Control, UAC, BitLocker, and VBS have different roles and prerequisites; being included does not mean uniformly enabled protection.
- It is not a cross-OS defense-rate comparison; desktop-app privileges and data access after login need separate consideration.

## Practical interpretation (7 lines)

- Separate Secure Boot, TPM, and VBS system protection from access to user files.
- Distinguish SmartScreen warnings, Smart App Control enforcement, and Defender detection.
- A process can read data available to its ordinary user without requesting UAC elevation.
- Do not assume privacy settings constrain every Win32 desktop application.
- BitLocker and Windows Hello do not comprehensively stop abuse of running apps or authenticated sessions.
- Consider managing agent work copies, credentials, and outbound destinations separately.
- The read-only inventory proposed below was not performed; no settings were changed and no attacks were run.

## Metadata and verification

- Original title: Windowsのセキュリティの仕組み - 標準機能と安全に使うための対策.
- Author: npaka. Published November 8, 2026 at 11:26 JST, as displayed.
- Type: personal explanatory article, not an academic paper or comparative benchmark; no DOI/arXiv ID.
- Checked: November 8, 2026 JST; current web text, without a fixed version number.
- Scope: requested article read through its end; selected Microsoft documentation checked for desktop permissions, UAC, Smart App Control, VBS/memory integrity, BitLocker, and firewall.
- Not performed: device configuration inspection, malware execution, defense measurement, or independent checking of every cited incident report.

## Question, method, and comparison conditions

The article introduces which attack stages and assets built-in Windows 11 controls address, and where additional care is needed. It combines feature descriptions, incidents, settings to inspect, and qualitative comparisons with Mac. It does not hold OS version, hardware, application type, and management policies constant in a controlled test.

This note supplements the article with official applicability documentation. Agent applications are proposals, not experimental results reported by the article.

## Claims and supporting evidence

| Layer | Features covered | Interpretation boundary |
|---|---|---|
| Boot and kernel | Secure Boot, Trusted Boot, TPM, VBS/HVCI | Distinguish boot validation, key/measurement protection, and isolated kernel code-integrity checks |
| Apps | Defender Antivirus, SmartScreen, Smart App Control | Detection, reputation checks, and execution control differ; check applicability and state |
| Permissions and data | UAC, app permissions, BitLocker, Windows Hello, passkeys | Separate elevation, access, encryption at rest, and authentication |
| Network | Windows Firewall, TLS/HTTPS, Wi-Fi/VPN | Traffic policy and channel encryption are different controls |

Microsoft documents exceptions to privacy controls for desktop applications. Obtaining an app from Microsoft Store does not alone establish a uniform sandbox or permission model. UAC governs use of administrator privileges; it does not automatically isolate information already accessible to a standard user.

Smart App Control combines safety predictions and signing with evaluation and enforcement modes. VBS/memory integrity depends on hardware and driver conditions. A device's Windows version, configuration, and management policies must be checked rather than assuming every feature is active.

BitLocker principally addresses exposure of stored data through loss or theft. Device encryption and conventional BitLocker management have different availability conditions. Windows Firewall can control both directions, but documented default policy allows outbound traffic; the feature's presence alone is not an exfiltration guarantee.

The article uses Lumma, ClickFix, and 3CX to illustrate theft, induced user actions, and compromised software distribution. Their scale and full detection histories were not independently verified here.

## Limitations

The strength/weakness ratings do not come with a common attack set, success rates, or repeated trials. They cannot establish general Windows-versus-Mac superiority. App model, edition, management settings, and update state change the conditions.

Even enabled OS controls do not settle whether an authorized user or agent can read and transmit secrets. HTTPS and VPN protection does not guarantee a destination's legitimacy or an application's intentions.

## Related notes and proposed application

- [Mac security layers](2026-npaka-macos-security-layers.md): maps protected assets and applicability in the companion article.
- [Trojan Horse repository poisoning](../agent-safety/2026-trojanforge-repository-poisoning.md): illustrates the separate problem of an agent taking instructions from external content.

Our proposed inventory separates agent workspaces, personal user files, Git/API credentials, and destinations. Avoiding administrator execution alone is not evidence that user data is isolated.

## Free verification proposal — not performed

Record the OS version/edition and displayed Windows Security, encryption, and firewall-profile states without changing them. Identify whether the chosen agent is a conventional desktop app or uses another isolation environment, then compare its execution identity and accessible workspace.

Do not include recovery keys, credentials, or private-file contents in the report. This inventory does not include toggling controls, rebooting, changing drivers, or running unknown software.

- Use status: proposed only; no device inspection or adoption.
- Next checks: actual app isolation, enabled protections, outbound rules, and boundaries between working data and secrets.

## Sources

- Requested explanatory article: [npaka](https://note.com/npaka/n/n45fc13b66f85)
- Primary documentation: [Desktop apps and privacy](https://support.microsoft.com/en-gb/windows/privacy/windows-desktop-apps-and-privacy?nochrome=true), [File-system exceptions](https://support.microsoft.com/en-us/windows/privacy/windows-file-system-access-and-privacy), [UAC](https://learn.microsoft.com/en-us/windows/security/application-security/application-control/user-account-control/)
- Primary documentation: [Smart App Control](https://learn.microsoft.com/windows/apps/develop/smart-app-control/overview), [Memory integrity](https://learn.microsoft.com/en-us/windows/security/hardware-security/enable-virtualization-based-protection-of-code-integrity)
- Primary documentation: [BitLocker](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/), [Firewall defaults](https://learn.microsoft.com/en-gb/windows/client-management/mdm/firewall-csp)
