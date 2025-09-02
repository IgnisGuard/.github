IgnisGuard

A modern approach to a Linux-based firewall appliance
- Leveraging modern Linux network technologies, such as
  - XDP / eBPF
  - nftables instead of iptables
- Focus on high performance >1G speeds
- Atomic OS upgrades
- API driven frontend
- Core services written in Rust
- A bloat-free base OS system, no PHP, Python, Perl, or other legacy tools installed.

While the distro is lean and fast, the goal is not to run this on low-powered devices, such as repurposing SOHO routers. 
This firewall distro/appliance is intended to be run on bare metal or being virtualized, running on AMD64/Arm64 hardware.
