# IgnisGuard

[![License: GPL-2.0](https://img.shields.io/badge/License-GPL%202.0-blue.svg)](https://www.gnu.org/licenses/gpl-2.0) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**IgnisGuard: A Modern, Lean Linux-Based Firewall Distro**  
IgnisGuard is a modern, lean Linux firewall OS built on nftables and XDP/eBPF, with Rust services and atomic, rollback-safe updates.

## Overview
IgnisGuard is a fresh take on firewall appliances: a small, hardened base, a fast data plane, and predictable operations. It targets contemporary hardware (bare metal or virtualized) on AMD64 and Arm64.

- Data plane: XDP/eBPF fast path, nftables control path
- Updates: immutable/atomic with rollback
- Services: Rust-first, with minimal dependencies
- Management: API-driven with a lightweight web UI and CLI

## Feature highlights

- Networking and firewall
  - Stateful filtering with nftables
  - NAT (SNAT/DNAT), port forwarding
  - IPv4 and IPv6 first-class (RA, DHCPv6-PD, planned)
  - VLANs, policy routing, multi-WAN (planned)
  - QoS/traffic shaping (tc, eBPF) (planned)
  - WireGuard VPN (planned)
- Performance
  - XDP/eBPF for high-throughput packet processing
- Operations
  - Atomic upgrades with rollback
  - Structured logs, metrics, and audit trail
- Security
  - Memory-safe userland (Rust) where practical
- Lean base image
  - No PHP, Python, Perl, or other unnecessary tools—just a clean, secure OS focused on firewall essentials, with a reduced attack surface.

## Non-goals

IgnisGuard does not target low-power SOHO routers or legacy 32-bit systems.
It favors clarity and performance over kitchen-sink extensibility.

## Security

If you believe you’ve found a vulnerability, please follow our responsible disclosure policy in SECURITY.md. Do not open public issues.

Telemetry: none by default. If optional metrics are added, they will be opt-in.

## Hardware requirements

- AMD64/Arm64, 2+ cores, 2 GB RAM minimum (4 GB recommended)
  
## Quick Start
1. **Installation**: Download the latest ISO from [releases](https://github.com/IgnisGuard/ignisguard/releases) and follow the [installation guide](docs/install.md).
2. **Configuration**: Use the frontend, API, or CLI tools to set up the configuration—see [docs](docs/) for examples.

## How it works

IgnisGuard uses XDP for early packet classification and a fast path, with
nftables managing stateful rules and forwarding. System updates are applied
atomically; rollback is instant if something goes wrong.

## Contributing
We welcome contributions! Check out our [contributing guidelines](CONTRIBUTING.md) for how to get involved. Report issues [here](https://github.com/IgnisGuard/ignisguard/issues) or join the discussion in [discussions](https://github.com/IgnisGuard/ignisguard/discussions).

## License
- Base OS/appliance (including ostree integrations): GPL-2.0 (see LICENSE-GPL). Combined images may be subject to GPL-2.0 terms.
- Custom Rust services/tools: MIT (see LICENSE-MIT).
- Source files include SPDX identifiers.
	
IgnisGuard is in very early development—feedback is appreciated.
