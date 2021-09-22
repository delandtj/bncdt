```
                                                     xxxxx
                                            xxx xxxxxx    x xxxx
                                           xx                  xxx
                                           x                     x
                                           x                   xxx
                                           x x             xxxxx
                                              xxx x    xxxxx
                                                   xx│xx
                                                     │
                                                     │
                                   ┌─────────────────┴────────────────────────┐
                                   │                                          │
                                   │                                          │
                                   │                                          │
   ┌──────────────┐   ┌────────────┴────────────┐                 ┌───────────┴─────────────┐
   │NAT/Firewall  │   │   Core                  │                 │   core                  │
┌──┤              ├───┤   Bancadati             │                 │   TLRE                  │
│  │              │   │                         │                 │                         │
│  └──────────────┘   │                         │                 │                         │
│                     └───┬───────────────────┬─┘                 └─────────────────────────┘
│          subnet1        │                   │   subnet2 (optional)ipv4)
│         ┌───────────────┴───┐           ┌───┴───────────────┐
│         │ XE Switch 1       │           │ XE switch 2       │
│         │                   │           │                   │
│         └───────┬───────────┘           └─────────────┬─────┘
│          vlan300│                              vlan301│
│                 │                                     │
│                 │       ┌─────────────────────┐       │                        Core:
│                 │       │                     │       │                          - per subnet an RA with  public IPv6
│                 │       │ NODE                │       │                          - 1 XE NIC on public segment IPv4
│                 │       │                     │       │
│                 │       │                     │       │                         All ports to nodes are access ports for the vlan
│                 └───────┤ XE NIC       XE NIC ├───────┘                         they participate in, so vlan numering is at your
│                         │                     │                                 discretion
│                         │                     │
│                         │                     │
│                         │                     │
│                         │                     │ 64/96 nodes ?
│                         │                     │
│                         │                     │
│                         └───┬────────────┬────┘
│                             │            │
│                       GE NIC│            │IPMI NIC
│                     vlan101 │            │vlan102
│                             │            │
│                         ┌───┴────────────┴────────────┐
│                         │   OOB Switch                │
└─────────────────────────┤                             │
                          │                             │
                          └──────────┬──────────────────┘
                                     │
                                     │
                            ┌────────┴────────┐
                            │ mgmt node       │
                            │ dhcp/pxe server │
                            └─────────────────┘
```
