<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">

</head>

<body>

<h2>Enterprise Factory Network Lab (Inter-VLAN routing using SVI)</h2>

<img src="Enterprise-Factory-Network-Lab.png" width="100%">

<h3>Highlights</h3>
<ul>
<li>Inter-VLAN routing using SVI (Layer 3 switching)</li>
<li>Centralized DHCP for multiple VLANs</li>
<li>HSRP for gateway redundancy</li>
<li>VLAN segmentation for departmental isolation</li>
<li>Port Security on access layer</li>
<li>DHCP Snooping to prevent rogue servers</li>
<li>Basic device hardening (console, VTY, enable secret, password encryption)</li>
</ul>

<h3>Network Architecture</h3>
<ul>
<li>Core Layer: 2 Multilayer switches (Layer 3 switching and routing)</li>
<li>Distribution Layer: Aggregation switches connecting access and core</li>
<li>Access Layer: Layer 2 switches connecting end devices</li>
</ul>

<p>
The design ensures structured traffic flow, scalability, and separation of responsibilities across layers.
</p>

<h3>VLAN Segmentation</h3>
<ul>
<li>VLAN 10 – Sales</li>
<li>VLAN 20 – IT</li>
<li>VLAN 30 – Production</li>
<li>VLAN 40 – HR</li>
<li>VLAN 50 – Admin</li>
<li>VLAN 100 – Servers</li>
</ul>

<p>
Each VLAN operates as an independent broadcast domain, improving security and network efficiency.
</p>

<h3>Key Configurations</h3>

<h4>Device Hardening</h4>
<ul>
<li>Hostname configuration for device identification</li>
<li>Secured privileged access using enable secret</li>
<li>Console, AUX, and VTY line passwords configured</li>
<li>Enabled service password-encryption</li>
<li>Login authentication enforced on all access lines</li>
</ul>

<h4>Inter-VLAN Routing (SVI)</h4>
<ul>
<li>Implemented using Switch Virtual Interfaces on multilayer switches</li>
<li>Enabled ip routing to allow communication between VLANs</li>
<li>Each VLAN assigned a dedicated gateway IP</li>
</ul>

<h4>DHCP (Centralized IP Management)</h4>
<ul>
<li>DHCP configured on core multilayer switch</li>
<li>Separate DHCP pools for each VLAN</li>
<li>Automatic IP assignment including gateway and DNS</li>
</ul>

<h4>Port Security (Access Layer)</h4>
<ul>
<li>Limits number of MAC addresses per port</li>
<li>Prevents unauthorized device connections</li>
<li>Sticky MAC learning enabled</li>
</ul>

<h4>DHCP Snooping</h4>
<ul>
<li>Enabled across all switches</li>
<li>Protects against rogue DHCP servers</li>
<li>Trusted ports configured on uplinks</li>
</ul>

<h4>Switching and Connectivity</h4>
<ul>
<li>Trunk links configured using 802.1Q between switches</li>
<li>VLAN traffic properly segmented across the network</li>
<li>Access ports assigned based on departmental VLANs</li>
</ul>

<h4>Testing and Validation</h4>
<ul>
<li>Verified inter-VLAN communication using ICMP (ping)</li>
<li>Confirmed DHCP IP assignment across all VLANs</li>
<li>Validated security features such as port restriction and DHCP filtering</li>
</ul>

</body>
</html>
