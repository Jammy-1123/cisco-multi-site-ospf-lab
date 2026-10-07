# cisco-multi-site-ospf-lab
Multi-site enterprise network simulation featuring VLANs, Router-on-a-Stick, and OSPF dynamic routing.
# Multi-Site Enterprise Network Lab (Cisco Packet Tracer)

## Overview
A simulated dual-site enterprise network infrastructure connecting a Head Office (HQ) and a Branch location over a routed WAN link using Cisco 2911 routers and 2960 switches.

## Network Topology & Design
- **HQ Site:**
  - **VLAN 10 (Management):** `192.168.10.0/24`
  - **VLAN 20 (Staff):** `192.168.20.0/24`
  - **Routing:** Router-on-a-Stick inter-VLAN routing on `R1-HQ` (`Gi0/0.10`, `Gi0/0.20`)
- **Branch Site:**
  - **VLAN 30 (Branch Staff):** `192.168.30.0/24`
  - **Routing:** Inter-VLAN sub-interface on `R2-Branch` (`Gi0/0.30`)
- **WAN Backbone:**
  - `10.0.0.0/30` interconnecting `R1-HQ` and `R2-Branch`
  - **Dynamic Routing:** OSPF Area 0 for cross-site reachability

## Key Features Configured
- **Switching:** IEEE 802.1Q trunking on switch-to-router links and access port assignments.
- **Routing:** Inter-VLAN sub-interface encapsulation (`encapsulation dot1Q`) and OSPF single-area dynamic routing.
- **Troubleshooting Executed:** Resolved sub-interface IP address overlapping errors (`192.168.20.0`) and validated initial ARP convergence timeouts across WAN boundaries.

## Verification
- End-to-end ping testing confirmed reachability from `PC-HQ-Staff` (`192.168.20.10`) to `PC-Branch-Staff` (`192.168.30.10`).
- Validated OSPF neighbor adjacency status (`FULL/DR`) between `1.1.1.1` and `2.2.2.2`.
