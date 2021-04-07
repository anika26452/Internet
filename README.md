# Internet

### How Does the Internet Work?

The Internet works through a packet routing network in accordance with the Internet Protocol (IP), the Transport Control Protocol (TCP) and other protocols.

### What is a protocol?

A protocol is a set of rules specifying how computers should communicate with each other over a network. For expample, *Transport Control Protocol*  has a rule that, if one computer sends data to another computer, the destination computer should let the source computer know if any data is missing, so source computer can resend it. Or the *Internet Protocol* which specifies how computers should route information to the other computers by attaching addresses onto the data it sends.

### What's a packet?

Data sent across the internet is called *message*. Before a *message* is sent, it is split in many fragments called **packets**. The maximum packet size is 1000 to 3000 characters. These packets are sent independently each other. **Internet Protocol** specifies how messages should be packeized.

### What's a packet routing Network?

It is a network that routes packets from source computer to destination computer. The internet is made up on a massive network of specialized computers called routers. Each routers job is to know how to move *packets* from the source computer to the destination computer. A packet will have moved through multiple routers during its journey. When a packet moves from one router to the next, it's called a hop. You can use the command-line tool *traceroute* to see the list of hops packets take between you and a host. The *internet protocol* specifies hownetwork address should be attached to the packet's headers, a designated space in the packet containing meta data. 

### Where did these internet routers come from? Who owns them?

A number of *Internet Service Proveider* corporation had added routers on ARPANET routers. There is no single owner of these routers: but rather multiple owners.

### Do the packets always arrive in order? If not, how is the messaege re-assemblesd?

The packets may arrive the destination out of order. But the packet's header contains information about the order of packets relative to the entire message. The *Transfer Control Protocol* uses this info to reconstruct the meassage in destination computer.

### Do packets always make it to their destination?

The *Internet Protocol* makes no guarantee that packets will always arrive in their destination. When that happens, it called a packet loss. This can happens when a router recieves more packets it can process. The *Transfer Control Protocol* handles packet loss by re-transmission. When two computers contact through *Transfer Control Protocol*, we say there is a *TCP* connection between them.

### What do these Internet Addresses look like?

These are called *IP Addresses* and there are two standards. The first address standard is *IPv4*. The format of *IPv4* is: 212.78.12.10. But because *IPv4* supports only 2³² possible address, so that the *Internet Task Force* proposed for a new address standard *IPv6*, which format is: 3ffe:1893:3452:4:345:f345:f345:42fc. *IPv6* supports 2¹²⁸ possible address. 
