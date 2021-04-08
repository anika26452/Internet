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

### How can there be over 8 billion networked devices on the Internet if there are only about 4 billion IPv4 addresses?

It's because there are public and private Ip addresses. Multiple devices on a local network connected to the Internet will share the same public IP address. Within the local network, these devices are differentiated from each other by private IP addresses, typically of the form 192.168.xx or 172.16.x.x or 10.x.x.x where x is a number between 1 and 255. These private IP addresses are assigned by Dynamic Host Configuration Protocol (DHCP).

### How does the router know where to send a packet?

Every router doesn't need to know where every  *IP Address* is. Is only need to know which oneof its neighbors, called an outbound link, to route each  packet to. *IP Addresses* can be broken down in two parts, a network prefix and a host idetifier. For example: The *IP Address* 192.32.45.01 can be broken into:
- Network Prefix: 192.32
- Host dentifier: 45.01

All network devices connect to the internet through a single connection will all share the same Network Prefix. Routers will send all packets f the form 192.32.*.*. to the same location. So instead of keeping track of billions of *IP Addresses*, routers only need to keep track millions of Network prefixes.

### But a router still need to know a lot of Network Prefixes? If a new router is added to the Internet how does it know how to handle packet for all these network prefixes?

A new router may come with a preconfigured routes. But if it encounters a packet it does not know how to route, it queries one of its neighboring router. If the router know how  to route the packet, that it sends that info back to the requesting router. The requesting router will save this info for future use.In this way, a new router builds up his own route table, a database of network prefixes to outbound links. If the neighboring router doesn't know it queries to its neighbors and so on.

### How do networked computers figure out ip addresses based on domain names?

We call looking up the *IP Address* of a human-readable domain name like [www.google.com](http://google.com) "resolving the IP address". Computer resolves IP Addresses through the *Domain Name System*. To resolve an IP address, the computer first checks its local DNS cache, which stores the *IP Address* of websites it has visited recently. If it can't find the *YP address* there or that *IP address* record has expired, it queries the ISP's DNS servers which are dedicated to resolving IP address. If ISP's DNS serves can't find the IP address, they query the **root name servers**, which can resolve evrey domain name for a given top-level domain. *.com*, *.net*, *.org* are some examples of top-level domains.

### How do applications communicate over the internet?

Like many other complex engineering projects, the internet is broken down into smaller independent componenets, which work together through well-defined interfaces. These components are called the internet network layers and they consist of *Link Layer*, *Internet Layer*, *Transport Layer* and *Application Layer*. They are called layers because they are built on top of each other; each layer uses the capabilities of the layers beneath it without worrying about its implementation details.

                          |    Layers   |
                          |-------------|
                          | Application |     Layer 4
                          |  Transport  |     Layer 3
                          |   Internet  |     Layer 2
                          |     Link    |     Layer 1

### What do each of these layers do?

At the lowest level is the *Link Layer* which is the "Physical Layer" of the internet. The *link layer* concerned with transmitting data bits through some physical medium like fiber-optic cables or wifi radio signals.

On top of the Link Layer is the *Internet Layer*. The Internet Layer is concerned with routing packets to their destinations. The Internet Protocol mentioned earlier lives in this layer. The Internet Protocol dynamically adjusts and reroutes packets based on network load or outages. Note it does not guarantee packets always make it to their destination, it just tries the best it can.

On top of the Internet Layer is the *Transport Layer*. This layer is to compensate for the fact that data can be loss in the Internet and Link layers below. The Transport Control Protocol mentioned earlier lives at this layer, and it works primarily to re-assembly packets into their original messages and also re-transmit packets that were loss. The Application Layer sits on top. This layer uses all the layers below to handle the complex details of moving the packets across the Internet. It lets applications easily make connections with other applications on the Internet with simple abstractions like sockets. The HTTP protocol which specifies how web browsers and web servers should interact lives in the Application Layer. The IMAP protocol which specifies how email clients should retrieve email lives in the Application Layer. The FTP protocol which specifies a file-transferring protocol between file-downloading clients and file-hosting servers lives in the Application Layer.
