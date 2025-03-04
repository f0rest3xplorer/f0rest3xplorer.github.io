---
icon: fas fa-flask
title: Homelab
permalink: /hl/
order: 3
mermaid: true
config:
    look: neo
    theme: neo
---

## Here is a basic map of my current home lab


```mermaid
graph TD
    A["Internet"] --> B["pfSense Router"]

    B -->|"WAN 192.168.1.106/24"| C["VLAN - WAN"]
    B -->|"LAN 10.0.0.1/24"| D["VLAN - LAN"]
    B -->|"ISOLATED 10.6.6.1/24"| E["VLAN - Isolated Network"]
    B -->|"AD_LAB 10.80.80.1/24"| F["VLAN - Active Directory Lab"]

    F -->|"Domain Controller"| G["Windows Server 2019 DC"]
    G --> H["Windows 10 Workstation 1"]
    G --> I["Windows 10 Workstation 2"]
    G --> J["Windows 11 Workstation"]
    
    K["Kali Linux Box"] --> |"Can connect to all 4 VLANs"| F
```

My lab currently consists of a virtualized pfsense router with four VLANs. I currently have an Active Directory lab set up with a Domain Controller running Windows Server 2019, two Windows 10 workstations, and one Windows 11 workstation. 

The Isolated VLAN has been set up for playing with intentionally vulnerable VMs, such as OWASP Juice Shop, machines from VulnHub, etc.

I am currently not using the other VLANs for anything, but wanted to practice setting up pfsense and building a network.

I am working on writing posts for some basic AD attacks and will hopefully start posting those here soon!