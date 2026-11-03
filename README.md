Wireshark Network Traffic Analysis: Ethernet Capture
1. Project Overview
This experiment uses Wireshark to capture and inspect packets
transmitted over an Ethernet network. The objective is to identify
common network protocols, understand their purposes, and compare the
traffic visible in two capture screenshots.
Important observation: Both supplied screenshots are labelled as
Ethernet captures. Therefore, this report compares two Ethernet
capture views/sessions. It does not establish a Wi-Fi-versus-Ethernet
performance comparison.

2. Objectives
- Capture live network traffic using Wireshark.
- Identify protocols appearing in the packet list.
- Understand the roles of MDNS, ARP, IPv4, IPv6, STP, and VRRP.
- Compare packet counts and visible traffic patterns between the two
  screenshots.
- Recognize what can and cannot be concluded from packet captures.
3. Tools and Environment
- Software: Wireshark
- Capture interface: Ethernet
- Operating system shown: Windows
- Traffic type: Local network and service-discovery traffic
4. Protocols Observed
  Protocol                            Purpose
  MDNS                                Multicast DNS allows devices to
discover services and hosts on a
local network without relying on a
conventional DNS server. It
commonly uses UDP port 5353.

  ARP                                 Address Resolution Protocol maps an
IPv4 address to a device's MAC
address on a local network.

  IPv4                                Internet Protocol version 4 carries
packets between devices using IPv4
addresses.

  IPv6                                Internet Protocol version 6 carries
packets using IPv6 addresses.

  STP                                 Spanning Tree Protocol helps
prevent Layer 2 switching loops in
bridged Ethernet networks.
VRRP                                Virtual Router Redundancy Protocol
provides router redundancy by
allowing routers to share a virtual
gateway address.
5. Screenshot 1: First Ethernet Capture
Observed packet count: Approximately 27,945 packets (as displayed in
the Wireshark status bar).

Visible observations:
- Multiple MDNS responses appear in the packet list.
- The selected packet is an MDNS response carried over UDP, with
  source and destination port 5353.
- ARP, IPv4, IPv6, and VRRP traffic are also visible.
- Several IPv6 fragment entries appear in the packet list.
- The MDNS responses include local service-discovery information.
Screenshot file to add to the repository:

images/ethernet_capture_1.png

6. Screenshot 2: Second Ethernet Capture
Observed packet count: Approximately 997 packets (as displayed in
the Wireshark status bar).

Visible observations:
- MDNS queries and responses are visible.
- The selected first packet is an STP packet.
- IPv4 and IPv6 packets appear in the capture.
- ARP and VRRP-related traffic are also visible.
- The packet list includes repeated MDNS queries for local
  service-discovery records.
Screenshot file to add to the repository:

images/ethernet_capture_2.png

7. Comparative Discussion
  Criteria                First capture           Second capture
  Interface shown         Ethernet                Ethernet

  Packets displayed in    27,945                  997
status bar                                      

  Main visible activity   Multiple MDNS responses MDNS queries and
responses

  Selected packet         MDNS response           STP packet

  Other visible protocols ARP, IPv4, IPv6, VRRP,  ARP, IPv4, IPv6, VRRP,
STP                     STP
General observation     Larger captured packet  Smaller captured packet
volume                  volume
The first screenshot contains approximately 27,945 captured packets,
whereas the second contains approximately 997. Both captures show local
network communication and service discovery using MDNS. The first
screenshot prominently displays MDNS responses, while the second shows
both MDNS queries and responses and has an STP packet selected.

The packet-count difference alone does not prove that one connection is
faster, slower, or more efficient. It may result from different capture
durations, network activity, selected interfaces, or capture conditions.
A fair performance comparison requires controlled tests using the same
website, comparable capture durations, and measurements such as
round-trip time, throughput, packet loss, and retransmissions.
8. Key Findings
1. MDNS traffic is visible in both captures, indicating local network
   service-discovery activity.
2. ARP traffic supports IPv4 address-to-MAC address resolution.
3. IPv4 and IPv6 traffic are both present.
4. STP and VRRP packets represent additional Layer 2 and
   network-redundancy control activity.
5. The two screenshots show different packet volumes, but packet volume
   by itself is not a network-performance metric.
9. Limitations
- Both screenshots appear to be Ethernet captures; a Wi-Fi capture is
  not provided.
- Capture durations and test conditions are not confirmed to be
  identical.
- The screenshots do not provide sufficient evidence to calculate
  throughput, latency, or packet-loss rates.
- A packet count is affected by background network activity and
  capture settings.
10. Conclusion
The Wireshark captures demonstrate how different protocols operate
within an Ethernet network. MDNS is used for local service discovery,
ARP resolves IPv4 addresses to MAC addresses, IPv4 and IPv6 carry
network traffic, STP helps prevent switching loops, and VRRP supports
gateway redundancy.

Although the first screenshot shows a much higher packet count than the
second, this difference should not be interpreted as a difference in
network speed. To compare Ethernet and Wi-Fi properly, capture traffic
separately on each interface under similar conditions and analyze
latency, throughput, packet loss, and retransmissions.
