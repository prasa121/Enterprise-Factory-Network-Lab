1. Network Architecture

  Core Layer: 2 Multilayer switches (Layer 3 switching & routing)
  Distribution Layer: Aggregation switches connecting access and core
  Access Layer: Layer 2 switches connecting end devices (PCs)
  
  The design ensures structured traffic flow, scalability, and separation of responsibilities across layers.

2. VLAN Segmentation

  The network is logically divided into multiple VLANs based on departments:
  
  VLAN 10 – Sales
  VLAN 20 – IT
  VLAN 30 – Production
  VLAN 40 – HR
  VLAN 50 – Admin
  VLAN 100 – Servers
  
  Each VLAN operates as an independent broadcast domain, improving security and network efficiency.

3. Key Configurations
   
  Inter-VLAN Routing (SVI)
    Implemented using Switch Virtual Interfaces (SVI) on core multilayer switches
    Enabled ip routing to allow communication between VLANs
    Each VLAN assigned a dedicated gateway IP
    
  DHCP (Centralized IP Management)
    DHCP configured on core multilayer switch
    Separate DHCP pools for each VLAN
    Automatic IP assignment including gateway and DNS
    
  Port Security (Access Layer)
    Limits number of MAC addresses per port
    Prevents unauthorized device connections
    Sticky MAC learning enabled
    
  DHCP Snooping
    Enabled across all switches
    Protects against rogue DHCP servers
    Trusted ports configured on uplinks
    
  Switching & Connectivity
    Trunk links configured using 802.1Q between switches
    VLAN traffic properly segmented and carried across the network
    Access ports assigned based on departmental VLANs
    
  Testing & Validation
    Verified inter-VLAN communication using ICMP (ping)
    Confirmed DHCP IP assignment across all VLANs
    Validated security features (port restriction and DHCP filtering)
