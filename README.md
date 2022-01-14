# evolution-of-evpn-rfcs

## RFC7209- Requirements for Ethernet VPN (EVPN)
* Describes the limitations of the widely-deployed technology VPLS, such as ‘redundancy, multicast optimization, and provisioning simplicity’.
* Cites deployment examples, such as data centre interconnect, as reasons for a new technology, Ethernet VPN, to address the limitations of VPLS.
* Uses MPLS terminology; LSP, CE, and PE.
* Details the feature requirements of this new technology, EVPN, such as flow-based load-balancing, all-active multihoming, ease of provisioning with auto-discovery of VPN members, and new service interface types.

## RFC 7364 -Problem Statement: Overlays for Network Virtualization
* Defines the rationale for virtual networks in multi-tenancy data centres now virtualization is wide-spread. Overlay networks are positioned as the basis for network virtualization, enabling tenant traffic separation.
* Somewhat similar to the concerns of MPLS L3VPNs but applied specifically to the data centre rather than a service provider core network.
* Companion piece to RFC 7365.

## RFC 7365 - Framework for Data Center (DC) Network Virtualization
* Provides the framework for Network Virtualization Overlay networks, to address the issues of virtualized data centres as raised in RFC 7364.
* Defines terms such as tenant systems and network virtualization edge (NVE) rather than relying on MPLS terminology such as CE and PE.
* Details a typical data centre architecture and reference model for network virtualization overlays.
* Concepts are defined in generic terms, not specific protocols or technologies. VPLS and EVPN are cited as possible implementations of L2 services, BGP/MPLS IP VPN for L3 services.

## RFC 7432 - BGP MPLS-Based Ethernet VPN
* Describes Ethernet VPN (EVPN) as a BGP MPLS-based solution to provide L2 services.
* EVPN is positioned in this context very much as a successor of VPLS, to address the limitations of that technology which are ‘important considerations for Data Center (DC) deployments’, but this document is not explicitly concerned with DC.
* Uses MPLS terminology, such as CE & PE.
* Defines the workings of EVPN; different types of service interface, route types 1 to 4, new BGP extended communities, convergence, BUM traffic forwarding, and Designated Forwarder election for multi-homed deployments.

## RFC 8365 - Network Virtualization Overlay Solution Using Ethernet VPN (EVPN)
* Specifies how EVPN can be used as a Network Virtualization Overlay solution.
* But rather than just using MPLS as the encapsulation technology, as in RFC 7432; VXLAN, NVGRE, and MPLS over GRE are covered, with an emphasis on VXLAN. Thus we see BGP EVPN VXLAN coming to the fore.
* Focus is very much on virtualized multi-tenancy data centres and terminology used reflects this; TS & NVE rather than CE & PE.
* Details the interworking of EVPN and VXLAN and uses VXLAN terms, such as VNI, rather than the generic NVO instance wording.
* Registers BGP Tunnel Encapsulation Attribute Tunnel Types for encapsulation types such as VXLAN, NVGRE, and MPLS.
* The solution detailed is for intra-subnet (layer 2) forwarding only.

## RFC 9135 - Integrated Routing and Bridging in Ethernet VPN (EVPN)
* Explains that EVPN thus far has been defined as a technology for intra-subnet connectivity (Layer 2), and describes an Integrated Routing and Bridging (IRB) for EVPN to enable inter-subnet connectivity (Layer 3).
* Introduces, and provides details of, both symmetric and asymmetric IRB. 
* Symmetric IRB is so named because the lookup operation on the ingress and egress PE are the same. With asymmetric IRB, the ingress PE performs and additional MAC lookup in the destination subnet, whereas the egress PE only performs a single MAC lookup.
* Describes the forwarding procedures of IRB for both the original model of EVPN using MPLS terms, such as PE & CE, but also specifically for tenant systems and NVEs in data centre networks.
* Registers a new BGP Extended Community for ‘EVPN Router's MAC’, this carries the MAC address to be used as the inner destination MAC for frames sent to the advertising PE when performing symmetric IRB.

## RFC 9136 - IP Prefix Advertisement in Ethernet VPN (EVPN) Companion
* Companion document to RFC 9136 that expands on EVPN’s IRB functionality by introducing a new route type, type 5, to advertise IP prefixes.
* Adds flexibility to EVPN IRB by decoupling the advertisement of IP prefixes from MAC addresses, as is the case with RT-2.
* Data centre focused examples used.

## Special mention - RFC 7348 Virtual eXtensible Local Area Network (VXLAN): A Framework for Overlaying Virtualized Layer 2 Networks over Layer 3 Networks
* Details VXLAN encapsulation type.
* Defines VXLAN frame format and data-centre focused deployment use cases.
* No mention of EVPN in this document.