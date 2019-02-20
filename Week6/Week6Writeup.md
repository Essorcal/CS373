# Week 6 - Windows Internals

## Intro

This week the focus was on network security which as I’ve come to learn is a whole different problem then application or OS security like we have gone over in previous weeks.  The biggest question posed was “Why do we need network security?” When we already have anti-virus software to facilitate malware detection/removal, several main reasons are as follows:
- Prevent unauthorized entry into network 
- Prevent unauthorized removal of data from machines within network
- Protect devices that do not have or cannont install anti-virus/malware protection
- Watch network traffic for suspicious activity

## Robustness Principle

<img src="robust.PNG" alt="robust" class="inline"/>

I agree with the vast majority of the robustness principle but in todays day and age I dont think it goes quite far enough in terms of security.  The main quote “Be liberal in what you accept, and conservative in what you send” is great for handling legacy protocols and ensuring all systems can talk to each other while at least trying to promote better practices and protocols by sending only what is required.  In previous decades when the internet was more of an ideal environment this was a perfectly fine solution since the internet is built on trust.  Nowadays with so many nefarious actors and so much of the world being run online as conservative an approach as possible seems to be the most prudent even if it would potentially make things more difficult in terms of communications between devices/networks.  The other portion I highlighted is in the same vein except at the time it was written the author couldn't have known what black hat hackers would think of in terms of exploits and malware that have done extreme finanical, political and industrial damage to governments and companies around the world.

## Firewalls

Firewalls are generally the first line of defense when it comes to network security. Cisco defines firewalls as https://www.cisco.com/c/en/us/products/security/firewalls/what-is-a-firewall.html network security devices that monitor and control ingoing and outgoing network traffic on a network. These control the policy which defines zones within a network and the traffic between those zones and the outside internet. Common zones include:
- Internet
- Intranet
- Corporate
- DMZ

This is just a small sample of possible zones they can include any sets of devices chosen by the policy.

## Defense In Depth

Defense in depth is the idea that multiple rings of security is much more secure then just a single defensive measure.  For example running a firewall, and an anti-virus software would give two layers of defense. Additional layers can be added in terms of intrusion detection, white and black listing, etc... The more layers of defense the higher the level of security; however, the more inconvenient dealing with that network could be.

## Networking Threats

There are many different ways networks can exploited just like there are so many ways applications can be exploited.

### Man in the Middle

A man in the middle attack is when something puts itself inbetween a packet's source and it's destination in order to either read or modify the data in the packets.  This can be used to steal information by just passively watching or by actively and modifying the payload.  Additionally this is how anti-virus solutions protect networks by being a passive listener checking to see if anything is changed.

### Spoofing

Spoofing is an attack where the attacker pretends to be a different device on the network in order to gain additional privileges or access that it doesn't have as itself.  One way of doing this is ARP (Address Resolution Protocol) poisoning is a type of spoofing falsifies messages on a network in order to pretend to be someone else on the network. Load testing can be a legitimate usage of spoofing in order to test a network's stability when it comes to handling a large number of simultaneous users.

### Denial of Service/Distributed Denial of Service 

A denial of service or distributed denial of service attack is about querying a network over and over in a short period of time either with one or multiple clients in order to overwhelm the networks resources and make it unusable or bring it offline.  This kind of attack has unfortunately become extremely popular over the last few years as the rise of bot nets has made the barrier of entry extremely low and inexpensive so at this point just about anyone can buy access to them.

## Networking Defenses

### Packet Filtering

Packet filtering is whitelisting expected traffic to only allow packets from sources that are trusted by the policy and stop anything from any other source.

### Deep Inspection

Deep inspections add additional inspections to the data portion of the packet as well  as the network headers.  This allows for IPS and data loss protection through signature/dictionary processing on content.

### Proxying

Proxying is a way of severing TCP connections and establishing new ones with additional inspection and modification of application data to prevent unauthorized access/manipulation.  The use of proxys does come with a performance hit in terms of latency as it involves an additional step between the packets being sent and received.
