---
layout: post
title: "The Internet.md"
---

# The Internet
Local Area network (LAN) => Wide Area Network (WAN) handled by ISP 

## Packets
Consists of:
- IP header
	- address etc.
- Data payload:
	- UDP (User Datagram Protocol) header
		- port number (can specify program that is using the internet)
		- checksum (verification)
	- or, TCP (Transmission Control Protocol) header
		- also contains port and checksum
		- sequential numbers of packets (knows what order of packets)
		- sends back an acknowledgement to verify (doubles messages and therefore bandwidth required)
	- Data
But how do you remember the address?
## Domain Name System (DNS)
- Send a domain name to the DNS server
- returns the desired address

Huge tree consisting of

Top Level domains:
- `.com`, `.gov`, `.au` etc.

Second Level domains:
- `google.com`, `twitch.io`

Sub-domain:
- `images.google.com`, `store.dftba.com`

Different DNS servers have authority over different parts over the tree.

Abstraction levels:
Physical Layer (electrical signals or wifi) < Data Link Layer (MAC Addresses, collision detection, etc) < Network Layer (Switching/routing) < Transport Layer (UDP/TCP) < Session Layer   



#notes/internet