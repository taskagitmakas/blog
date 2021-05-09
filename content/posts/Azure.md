title: "Azure"
date: 2020-05-09T08:34:33+08:00
draft: false
featuredImg: ""
tags: 
  - VERSA
  - 101
  - SDWAN
  - Ubuntu
  - Linux
---

ExpressRoute premium
What is ExpressRoute premium?
ExpressRoute premium is a collection of the following features:

Increased routing table limit from 4000 routes to 10,000 routes for private peering.

Increased number of VNets and ExpressRoute Global Reach connections that can be enabled on an ExpressRoute circuit (default is 10). For more information, see the ExpressRoute Limits table.

Connectivity to Microsoft 365

Global connectivity over the Microsoft core network. You can now link a VNet in one geopolitical region with an ExpressRoute circuit in another region.
Examples:

You can link a VNet created in Europe West to an ExpressRoute circuit created in Silicon Valley.
On the Microsoft peering, prefixes from other geopolitical regions are advertised such that you can connect to, for example, SQL Azure in Europe West from a circuit in Silicon Valley.
How many VNets and ExpressRoute Global Reach connections can I enable on an ExpressRoute circuit if I enabled ExpressRoute premium?
The following tables show the ExpressRoute limits and the number of VNets and ExpressRoute Global Reach connections per ExpressRoute circuit:

HOW MANY VNETS AND EXPRESSROUTE GLOBAL REACH CONNECTIONS CAN I ENABLE ON AN EXPRESSROUTE CIRCUIT IF I ENABLED EXPRESSROUTE PREMIUM?
Resource	Limit
ExpressRoute circuits per subscription	10
ExpressRoute circuits per region per subscription, with Azure Resource Manager	10
Maximum number of routes advertised to Azure private peering with ExpressRoute Standard	4,000
Maximum number of routes advertised to Azure private peering with ExpressRoute Premium add-on	10,000
Maximum number of routes advertised from Azure private peering from the VNet address space for an ExpressRoute connection	1,000
Maximum number of routes advertised to Microsoft peering with ExpressRoute Standard	200
Maximum number of routes advertised to Microsoft peering with ExpressRoute Premium add-on	200
Maximum number of ExpressRoute circuits linked to the same virtual network in the same peering location	4
Maximum number of ExpressRoute circuits linked to the same virtual network in different peering locations	16 (For more information, see Gateway SKU.)
Number of virtual network links allowed per ExpressRoute circuit	See the Number of virtual networks per ExpressRoute circuit table.
Number of virtual networks per ExpressRoute circuit
NUMBER OF VIRTUAL NETWORKS PER EXPRESSROUTE CIRCUIT
Circuit size	Number of virtual network links for Standard	Number of virtual network links with Premium add-on
50 Mbps	10	20
100 Mbps	10	25
200 Mbps	10	25
500 Mbps	10	40
1 Gbps	10	50
2 Gbps	10	60
5 Gbps	10	75
10 Gbps	10	100
40 Gbps*	10	100
100 Gbps*	10	100
*100 Gbps ExpressRoute Direct Only

 Note

Global Reach connections count against the limit of virtual network connections per ExpressRoute Circuit. For example, a 10 Gbps Premium Circuit would allow for 5 Global Reach connections and 95 connections to the ExpressRoute Gateways or 95 Global Reach connections and 5 connections to the ExpressRoute Gateways or any other combination up to the limit of 100 connections for the circuit.

