# Multi-Router OSPF Enterprise

_Level: advanced — Enterprise Campus & LAN — OSPFv2 · Multi-Area OSPF · Router ID · Passive Interfaces · Cost Tuning_

**Status: Verified.** Completed on 2026-11-24; every requirement was machine-checked against the network built in BuildTheNet and passed.

Snapshot taken 2026-11-24. Built in a simulation — no physical or production equipment was involved.

## Scenario

Dunmore Builders' Merchants has four depots, each with its own router, and a ring of links between them. The static routes have been wrong twice this year. Replace them with OSPF.

### Why it matters

Static routes stop scaling at about the third site. OSPF is the CCNA answer, and the parts people get wrong are router IDs, wildcard masks and passive interfaces.

## Requirements

| # | Requirement | Status | Checked by |
|---|---|---|---|
| 1 | Build at least four routers with LANs and inter-router links. | Passed | Sandbox check |
| 2 | Enable OSPF on every router with an explicit router-id. | Passed | Sandbox check |
| 3 | Advertise the connected networks with correct wildcard masks. | Passed | Sandbox check |
| 4 | Make LAN interfaces passive so no adjacency is attempted toward hosts. | Passed | Sandbox check |

## Topology

![Topology diagram](topology.svg)

## Addressing

| Device | Interface | Address | Mask | Mode | Gateway |
|---|---|---|---|---|---|
| Router-1 | Gi0/0 | 192.168.10.1/24 | 255.255.255.0 | routed |  |
| Router-1 | Gi0/1 | 10.0.10.1/30 | 255.255.255.252 | routed |  |
| Router-1 | Gi0/2 | 10.0.40.2/30 | 255.255.255.252 | routed |  |
| Router-2 | Gi0/0 | 192.168.20.1/24 | 255.255.255.0 | routed |  |
| Router-2 | Gi0/1 | 10.0.10.2/30 | 255.255.255.252 | routed |  |
| Router-2 | Gi0/2 | 10.0.20.1/30 | 255.255.255.252 | routed |  |
| Router-3 | Gi0/0 | 192.168.30.1/24 | 255.255.255.0 | routed |  |
| Router-3 | Gi0/1 | 10.0.30.1/30 | 255.255.255.252 | routed |  |
| Router-3 | Gi0/2 | 10.0.20.2/30 | 255.255.255.252 | routed |  |
| Router-4 | Gi0/0 | 192.168.40.1/24 | 255.255.255.0 | routed |  |
| Router-4 | Gi0/1 | 10.0.30.2/30 | 255.255.255.252 | routed |  |
| Router-4 | Gi0/2 | 10.0.40.1/30 | 255.255.255.252 | routed |  |

## Device configurations

Running-configs as `show running-config` prints them in the BuildTheNet sandbox. Passwords, secrets, keys and SNMP communities are replaced with `<removed>`.

- [Router-1](configs/Router-1.txt)
- [Router-2](configs/Router-2.txt)
- [Router-3](configs/Router-3.txt)
- [Router-4](configs/Router-4.txt)
- [Switch-1](configs/Switch-1.txt)
- [Switch-2](configs/Switch-2.txt)
- [Switch-3](configs/Switch-3.txt)
- [Switch-4](configs/Switch-4.txt)

---

Built on [BuildTheNet](https://www.buildthenet.io/projects/proj-pt-14-ospf-enterprise)
