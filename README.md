# Internet

### How Does the Internet Work?

The Internet works through a packet routing network in accordance with the Internet Protocol (IP), the Transport Control Protocol (TCP) and other protocols.

### What is a protocol?

A protocol is a set of rules specifying how computers should communicate with each other over a network. For expample, *Transport Control Protocol*  has a rule that, if one computer sends data to another computer, the destination computer should let the source computer know if any data is missing, so source computer can resend it. Or the *Internet Protocol* which specifies how computers should route information to the other computers by attaching addresses onto the data it sends.

### What's a packet?

Data sent across the internet is called *message*. Before a *message* is sent, it is split in many fragments called **packets**. The maximum packet size is 1000 to 3000 characters. These packets are sent independently each other. **Internet Protocol** specifies how messages should be packeized.

### What's a packet routing Network?

It is a network that routes packets from source computer to destination computer. The internet is made up on a massive network of specialized computers called routers. Each routers job is to know how to move *packets* from the source computer to the destination computer. A packet will have moved through multiple routers during its journey. When a packet moves from one router to the next, it's called a hop. You can use the command-line tool *traceroute* to see the list of hops packets take between you and a host. The *internet protocol* specifies hownetwork address should be attached to the packet's headers, a designated space in the packet containing meta data. 
