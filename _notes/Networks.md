---
layout: post
title: "Networks"
---

# Networks
## LAN (Local Area Network)
Essentially just wires between devices

- E.g. Ethernet, WiFi
- Uses addresses so that computers in the network know what data is for them. This is called a MAC (Media Access Control) Address
- if two computers try to send messages simultaneously it results in a collision
- Can fix by:
1. If network is busy wait a random time interval and try again
2. Use network switches
	- split network into subnetworks connected by switches
	- This means that a message within a subnetwork will not make the whole network busy
- With many network switches, there may be multiple ‘routes’ between two computers
## Routing
How can we solve routing?
- circuit switching
	- switch whole circuits to get to correct address
	- expensive and inflexible
- message switching
	- use message routers (essentially graph vertices)
	- store a ‘hop’ count
	- if there is a routing error, hop count will keep increasing
	- use a hop limit
- big messages can clog up networks
		- split it up into packets containing address and data
		- the format is defined by the ‘internet protocol’ (IP)

#notes/internet