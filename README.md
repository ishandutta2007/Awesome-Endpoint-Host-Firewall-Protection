# Awesome-Endpoint-Host-Firewall-Protection

# Awesome-Endpoint-Host-Firewall-Protection

**Top Endpoint Host Firewall Protection (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Host-Based Firewalls, Application Control, Egress Filtering & Self-Hosted Endpoint Defense*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Endpoint Host Firewall Protection**. These tools enable organizations to control network traffic at the host level—blocking malicious connections, restricting application egress, and enforcing network segmentation on endpoints—from fully managed enterprise suites with cloud-managed policies to open-source firewalls that give teams complete control over their host defense.



**Examples** include CrowdStrike Falcon Firewall Management, Microsoft Defender Firewall, Sophos Endpoint Firewall, Symantec Client Firewall, Trellix Endpoint Firewall, Bitdefender GravityZone, Comodo Firewall, ZoneAlarm Business, Kaspersky Endpoint Security, and Check Point Endpoint Security (the category leaders in commercial space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted endpoint firewalls, egress control, and open host defense. **Critical note**: The open-source landscape is genuinely functional—**SysWarden** provides auditable nftables enforcement with fail-closed design , **Portmaster** offers application-level egress control with privacy features , and **OpenSnitch** derivatives deliver interactive per-connection prompts . No open-source project matches CrowdStrike's cloud-managed policy orchestration across thousands of endpoints, but for single-host or small-fleet protection, the options are production-capable.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **CrowdStrike Falcon Firewall Management**

  **Cloud-managed host firewall** within Falcon platform. **Pricing**: **Falcon Go free** (100 devices, includes firewall management); **Pro $14.99/device/month** or **$99.99/year**; **Enterprise $19.99/month** or **$184.99/year** . **Free tier**: Yes, 100 devices on Falcon Go. **Best for**: CrowdStrike customers wanting firewall policies managed alongside EDR—**trade-off**: requires Falcon agent; full features need paid tiers.



- **Microsoft Defender Firewall**

  **Built-in Windows firewall** with advanced security management. **Pricing**: **Free with Windows 10/11**; **Microsoft Defender for Business $2.94/user/month** (annual) or **$1.40/user/month** add-on for cross-platform management . **Free tier**: Yes, fully featured on Windows. **Best for**: Windows-centric organizations wanting native firewall without additional cost—**trade-off**: Windows-only for the free version; cross-platform requires paid tier.



- **Sophos Endpoint Firewall**

  **Host firewall within Sophos Intercept X**. **Pricing**: Quote-only; bundled with endpoint protection. **Free tier**: Trial available. **Best for**: Sophos customers wanting integrated endpoint and firewall management.



- **Symantec Client Firewall** (Broadcom)

  **Endpoint firewall** within Symantec Endpoint Protection. **Pricing**: Quote-only. **Free tier**: None. **Best for**: enterprises with existing Broadcom/Symantec investments—**trade-off**: product roadmap uncertainty.



- **Trellix Endpoint Firewall**

  **Host firewall** within Trellix endpoint security suite. **Pricing**: Quote-only. **Free tier**: None. **Best for**: enterprises with existing Trellix investments.



- **Bitdefender GravityZone Firewall**

  **Host firewall** within GravityZone platform. **Pricing**: Quote-only; tiered by features. **Free tier**: Trial available. **Best for**: organizations wanting integrated endpoint security with firewall.



- **Comodo Firewall**

  **Endpoint firewall** with default-deny and sandboxing. **Pricing**: **Free version available**; paid business plans quote-based. **Free tier**: Yes, free for personal use. **Best for**: users wanting aggressive default-deny protection—**trade-off**: false positives; business features require paid plans.



- **ZoneAlarm Business**

  **Endpoint firewall** with advanced threat protection. **Pricing**: Quote-only; tiered by users. **Free tier**: Free personal version exists. **Best for**: SMBs wanting firewall with application control.



- **Kaspersky Endpoint Security**

  **Endpoint protection** with host firewall. **Pricing**: Quote-only. **Free tier**: Trial available. **Best for**: organizations wanting integrated endpoint security—**trade-off**: geopolitical concerns may limit adoption.



- **Check Point Endpoint Security**

  **Enterprise endpoint security** with firewall and threat prevention. **Pricing**: Quote-only. **Free tier**: None. **Best for**: Check Point customers wanting unified endpoint and network security.



## Open-Source GitHub Projects



- **SysWarden**

  **Host-local Linux defense with auditable nftables enforcement** (open source, v4.10.4) — **the most rigorous open-source host firewall** for operators wanting reviewable, fail-closed defense . **Features**: **Authoritative nftables policy** with bounded firewalld and UFW compatibility when exactly one frontend is active; **persistent blocklists, whitelists, and SSH exceptions** with canonical IP, CIDR, and service-scoped entries; **host telemetry and out-of-band WAAP log analysis**; **bounded threat-intelligence feeds** with last-known-good behavior; **native terminal dashboard**—no browser service or listening port; **authenticated HA synchronization** over TLS 1.3; **BunkerWeb integration** with provenance-aware cleanup; native DEB, RPM, APK packaging . **Supply chain**: checksummed packages, signed update metadata, SPDX SBOM, Ed25519-signed manifests . **Tech stack**: Linux (nftables). **Deploy**: Self-hosted (Linux amd64, packages). **Trade-off**: **Linux-only**; no Windows or macOS support; operator-oriented (CLI/TUI, not a consumer GUI). **Best for**: Linux operators wanting one reviewable, auditable host defense layer with fail-closed enforcement—especially those who need to prove what was blocked and why.



- **Portmaster**

  **Open-source application firewall for Windows and Linux** (open source, EU-developed) — **the most user-friendly open-source endpoint firewall**, focused on privacy and per-app control . **Features**: **Monitor all network activity**—every packet is visible and can be stopped; **per-app rules**—define allowed network scopes (localhost, LAN, internet, P2P, inbound); **automatic blocking** of trackers, malware, and ads via filter lists; **secure DNS** (DoH/DoT) with DNS rebinding protection; **network history** with searchable local database; **per-app bandwidth usage**; **special process support**—Snap, AppImage, scripts on Linux; Windows Store apps and svchost.exe on Windows . **Architecture**: nfqueue on Linux, kernel driver (WFP) on Windows; eBPF and /proc for connection ownership on Linux . **Tech stack**: Go. **Deploy**: Desktop application (Windows, Linux). **Trade-off**: **No central management**—each host must be configured independently; no cloud orchestration. **Best for**: privacy-conscious users and small teams wanting per-application egress control without enterprise complexity—especially those wanting to see and block what apps are doing.



- **OpenShield (OpenSnitch derivative)**

  **Interactive application firewall with learning mode** (open source) — **the most feature-rich interactive firewall** for Linux, forking OpenSnitch with enhanced security controls . **Features**: **Learning mode** builds rules from observed connections; **Enforcing mode** with Strict and Fast strategies; **Strict** (default) exhaustively verifies process ownership; **Fast** caches ownership hints for performance—explicitly a weaker guarantee ; **Fail-closed BlockAll quarantine** on unsafe outcomes; **per-process rules** with executable path, UID, and optional argv/cgroup; **packet verdicts are never cached**—current rules always apply . **Tech stack**: Linux (nftables, NFQUEUE). **Deploy**: Self-hosted (Linux). **Trade-off**: **Linux-only**; interactive prompts require user attention during learning; Fast mode trades security for performance. **Best for**: Linux users wanting granular per-connection control with a learning curve that builds rules from actual behavior—especially those who want to review and approve connections interactively.



- **netxfw**

  **eBPF/XDP-based Linux host firewall** (open source, v0.4.0) — **the highest-performance open-source firewall**, processing packets at the network driver layer . **Features**: **XDP-based packet processing**—drops malicious packets at the driver level, bypassing the kernel network stack with minimal CPU overhead; **IPv4 and IPv6 support** with CIDR blocking; **automatic interface detection**; **Prometheus exporter** for drop rates and traffic trends; **one-command blocking** (`netxfw lock <IP>`) with dynamic rule loading; **YAML configuration** for cloud-native integration . **Tech stack**: Go, eBPF/XDP. **Deploy**: Self-hosted (Linux kernel 5.4+). **Trade-off**: **Firewall only**—no application-level control or process attribution; best for network-layer DDoS and scan blocking, not per-app egress. **Best for**: Linux servers needing high-performance network-layer protection against DDoS, brute force, and scanning—especially those wanting eBPF performance without complex configuration.



### Additional Strong Open-Source Options



- **pfSense / OPNsense** — FreeBSD-based firewall distributions (Apache 2.0 / BSD). Full-featured network firewalls with web UI, stateful inspection, VPN, and IDS/IPS. **Note**: **Network perimeter firewalls**, not host-based endpoint firewalls—they protect networks, not individual endpoints . **Best for**: network perimeter defense, not endpoint protection.

- **UFW / firewalld** — Linux host firewall frontends (GPL). Simple iptables/nftables management. **Note**: **Basic port-based firewalls**—no application control or per-process rules. **Best for**: basic host network protection on Linux servers.



**Frameworks for building custom systems**: Combine **SysWarden** for auditable nftables enforcement with **Portmaster** for application-level egress control and **netxfw** for high-performance DDoS protection—creating a layered Linux host defense stack. **None of these match CrowdStrike's cloud-managed fleet orchestration**, but for single-host or small-fleet protection, the options are production-capable.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Endpoint firewall platforms handling network policies must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls.

- **The "network perimeter firewall" vs. "host-based endpoint firewall" vs. "application firewall" distinction is critical.** **pfSense and OPNsense** are **network perimeter firewalls**—they protect entire networks, not individual endpoints . **Microsoft Defender Firewall, Sophos, Symantec, and Trellix** are **host-based endpoint firewalls**—they run on each endpoint and enforce per-host policies . **Portmaster and OpenShield** are **application firewalls**—they add per-process control and egress filtering . **SysWarden and netxfw** are **host firewalls**—they enforce nftables/XDP rules on Linux hosts . **Choose based on whether you need network defense, host-level port control, or per-application egress.**

- **SysWarden is the most rigorous open-source host firewall** for auditable, fail-closed Linux defense—with SBOM, signed manifests, and operator guidance . **The trade-off**: Linux-only, operator-oriented (TUI, not GUI).

- **Portmaster is the most user-friendly open-source application firewall**—per-app rules, automatic tracker blocking, secure DNS, and network history for Windows and Linux . **The trade-off**: no central management; each host is configured independently.

- **OpenShield's Fast mode is a deliberate security tradeoff**—it caches ownership hints and can miss same-UID extra owners that Strict would detect . **Use Strict when exhaustive matching-UID owner discovery is required** .

- **netxfw is for network-layer defense, not application control.** It drops packets at XDP with minimal CPU overhead—ideal for DDoS and scanning—but does not know which process sent a packet . **Pair it with an application firewall for full coverage.**

- **Microsoft Defender Firewall is free and fully featured on Windows**—the most cost-effective option for Windows endpoints . **Cross-platform management requires Microsoft Defender for Business at $2.94/user/month** .

- **CrowdStrike Falcon Go includes firewall management free for up to 100 devices**—the most generous commercial entry point . **Pro at $14.99/device/month** adds full features.

- Self-hosted open-source solutions require proper setup, kernel compatibility (Linux 5.4+ for netxfw), and ongoing maintenance. **Host firewalls control network access**—ensure your deployment meets your organization's security standards before enforcing policies on production endpoints.



---



**Made for security engineers, system administrators, and organizations building transparent endpoint firewall solutions.**

Let's make Endpoint Host Firewall Protection more open, data-driven, and network-aware.
