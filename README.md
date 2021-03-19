# netwhat
As the subject says, this project is an introduction to network problematics.
Unlike other projects, where we have to code, now we have to read and study everything we find on the Internet about networks to end up taking an exam where we demonstrate the skills and knowledge we have acquired.

### How have I done this project?
Since this is not a coding project, I have read a lot of documentation that I want to put here so that you can study it too. I have to write a lot of things, so I apologize if I have some spelling errors, I am Spanish. :)
At the end of the explanation you will have some resources to continue studying networks. Most of them are the ones that I have read to prepare for my exam.

### What is an IP address?
An IP address is <b>a unique address that identifies a device on the Internet or a local network.</b> IP stands for "Internet Protocol", which is the set of rules governing the format of data sent via the internet or local network. In essence, IP addresses are the identifiers that allows information to be sent between devices on a network: they contain location information and make devices accessible for communication. The Internet needs a way to differentiate between different computers, routers and websites.<br>
<br>
An IP address is a string of numbers separated by periods. IP addresses are expressed as a set of four numbers <b>(IPv4).</b> Each number in the set can range from <b>0 to 255</b>. So the full IP addressing range goes from 0.0.0.0 to 255.255.255.255. An example of an IP address can be: 192.168.128.144.<br>
<br>
<b>IPv4</b> was the first version of IP. It was deployed for production in the ARPANET in 1983. Todays it is most widely used IP version. The IPv4 uses a <b>32-bit address scheme,</b> as we seen above, allowing to store 2^32 addresses which is more than 4 billion addresses. Till date, it is considered the primary Internet Protocol and carries 94% of Internet traffic.
In addition, <b>IPv6</b> is the most recent version of the Internet Protocol. This new IP address version if being deployed to fulfill the need for more Internet addresses. It was aimed to resolve issues which are associated with IPv4. With 128-bit address space, it allows 340 undecillion unique address space.<br>
<br>

### What is a Netmask?
A <b>Netmask is a 32-bit "mask"</b> used to divide an IP address into subnets and specify the network's available hosts. In a netmask, two bits are always automatically assigned. For example, in 255.255.255.0, "0" is the <b>assigned network address.</b> In 255.255.255.255, "255" is the <b>assigned broadcast address.</b> The 0 and 255 are always assigned and cannot be used.<br>
<br>
Netmask defines how large a network is or if you are configuring a rule that requires an IP address and a Netmask, the Netmask wil signify to what range of the Network the rule will apply to:

IP             | NETMASK         | DESCRIPTION
:------------- | :-------------- | :-----------------------------------------
192.168.55.161 | 255.255.255.255 | Only applies to 192.168.55.161
192.168.55.0   | 255.255.255.0   | Applies to IPs in the 192.168.55.255 range
192.168.55.240 | 255.255.255.240 | 192.168.55.240 - 192.168.55.255
192.168.55.161 | 255.255.255.0   | 192.168.55.0 - 192.168.55.255
192.168.0.0    | 255.255.0.0     | 192.168.0.0 - 192.168.255.255

Sometimes you will see that a Netmask is defined by one number. This number is the length of the Netmask in bits:

NETMASK        | 255 | 255 | 255 | 255
:------------- | :-- | :-- | :-- | :--
Netmask length | 8   | 16  | 24  | 32

### What is the subnet of an IP with Netmask?
The <b>subnet mask splits the IP address into the host and network addresses,</b> thereby defining which part of the IP address belongs to the device and which part belongs to the network. The device called a <b>gateway</b> or <b>default gateway</b> connects local devices to other network. This means that when a local device wants to send information to a device at an IP address on another network, it first sends its packets to the gateway, which then forwards the data on to its destinatino outside of the local network.<br>
<br>
A <b>subnet mask</b> is a 32-bit number created by setting host bits to all 0s and setting network bits to all 1s. In this way, the subnet mask separates the IP address into the network and the host addresses. The IP address, subnet mask and gateway or router comprise an underlying structure -the Internet Protocol- that most networks use to facilitate inter-device communication.<br>
When organizations need additional subnetworking, subnetting divides the host elements of the IP address further into a subnet. <b>The goal of subnet masks are simply to enable the subnetting process.</b><br>
<br>
<b>Subnetting is the technique for logically partitioning a single physical network into multiple smaller sub-networks or subnets.</b> Subnetting enables an organization to conceal network complexity and reduce network traffic by adding subnets without a new network number. When a single network number must be use across many segments of a local area network (LAN), subnetting is essential.

### What is the broadcast address of a subnet?
<b>Broadcasting in a computer network is transmitting a message, which does not require a response, to all users of the network.</b> One computer in a network sends a data packet to all other users at the same time. The sender does not need to indicate recipient addresses - this is how the broadcast differs from unicast, where only a signle known recipient is addressed. The general advantage of broadcasting is that information can be distributed without having to be transmited multiple times.<br>
<br>
A special address is required to carry out this procedure, which replaces the recipient addresses in question. This broadcast IP is of particular use if the addresses of the individual network users are not known. The sender initiates the broadcast connection and provides the address at which the recipients can contact them. A broadcast works in a similar way to a mailing list: the recipients are not visible to each other and the sender has no way of knowing the addresses of the network users. Only if the users contact the sender one-to-one do they disclose their own address.

### What are the different ways to represent an ip address with the Netmask?
Each address space is divided into a network portion and a host portion. The amount the address that each of these take up is dependent on the class that the address belongs to. For instance, for class C addresses, the first 3 octets are used to describe the network.<br>
By default, each network has only one subnet, which contains all of the host addresses defined within. A netmask is basically a specification of the amount of address bits that are used for the network portion. A subnet maskis another netmask within used to further divide the network.<br>
<br>
Each bit of the address that is considered significan for describing the network should be represented as a "1" in the netmask. For instande, the address 192.168.0.15 can be expressed like this, in binary:

    1100 0000 . 1010 1000 . 0000 0000 . 0000 1111
    
As we described above, the network portion for class C addresses is the first 3 octets, or the first 24 bits. Since these are the significant bits that we want to preserve, the netmask would be:

    1111 1111 . 1111 1111 . 1111 1111 . 0000 0000
    
This can be written in the normal IPv4 format as 255.255.255.0. Any bit that is a "0" in the binary representation of the netmask is considered part of the host portion of the address and can be variable. The bits that are "1" are static, however, for the network or subnetwork that is being discussed.<br>
We determine the network portion of the address by applying a bitwise AND operatoin between the address and the netmask. A bitwise AND operation will basically save the networking portion of the address and discard the host portion. The result of this on our above example that represent our network is:

    1100 0000 . 1010 1000 . 0000 0000 . 0000 0000
    
This can be expressed as <>192.168.0.0</b>. The host specification is then the difference between these original value and the host portion. In our case, the host is <b>0000 1111</b> or <b>15</b>.<br>
<br>
A system called <b>Classless Inter-Domain Routing, or CIDR,</b> was developed as an alternative to traditional subneting. The idea is that you can add a specification in the IP address itself as to the number of significant bits that make up the routing or networking portion. For example, we could express the idea that the IP address <b>192.168.0.15</b> is associated with the netmask <b>255.255.255.0</b> by using the CIDR notation of <b>192.168.0.15/24.</b> This means that the first 24 bits of the IP address are considered significant for the network routing.

### What are the differences between public and private IPs?
All IPv4 addresses can be divided into two major groups: <b>global and private.</b> Global (or public, external) addresses can also be called <b>WAN addresses</b>, and they are used on the Internet. Private (or local, internal) addresses are used in the <b>local network (LAN)</b>.
##### Public IP addresses
These are public addresses that are used on the Internet. <b>A public IP address is an IP address that is used to access the Internet.</b> Public IP addresses can be routed on the Internet, unlike private addresses. The presence of a public IP address on you router or computer will allow you to organize your own server, remote access to your computer, video surveillance cameras, and get access to them from anywhere on the global network.<br>
With a public IP address, you can set up any home server to publish it on the Internet: Web, VPN, FTP, etc.<br>
<br>
For home users, an ISP can provide one or more public IP addresses. Due to the limited number of public IP addresses and the increasing number of Internet users, ISPs are now more common to give private IP addresses to subscribers.

##### Private IP addresses
<b>Private addresses are not routed on the Internet and no traffic can be sent to them from the Internet</b>, they only supposed to work within the local network. Private addresses include IP addresses from the following subnets:
<ul>
    <li>Range from 10.0.0.0 to 10.255.255.255 ---> Network: 10.0.0.0     Mask: 255.0.0.0 or /8</li>
    <li>Range from 172.16.0.0 to 172.31.255.255 ---> Network: 172.16.0.0     Mask: 255.240.0.0 or /12</li>
    <li>Range from 192.168.0.0 to 192.168.255.255 ---> Network: 192.168.0.0     Mask: 255.255.0.0 or /16</li>
</ul>
Those are <b>reserved</b> IP addresses. These addresses are intended for use in closed local area networks and the allocation of such addresses is not globally controlled by anyone. Direct access to the Internet from a private IP address is not possible. In this case, the connection to the Internet must go through <b>NAT (Network Address Translation replaces the private IP address with a public one)</b>. Private IP addresses within the same local network must be unique and cannot duplicate.<br>
<br>
As far as Internet security is concerned, the use of a <b>private IP address is more secure than the use of a public IP address</b>, as private IP addresses are not directly visible on the Internet and are located behind NAT, which also ensures the security of the home network. When using a public IP address, measures are required to provide additional security for the computer or server that are exposing their services to the Internet (e.g. firewalls).

### What is a class of IP addresses?
TCP/IP defines five classes of IP addresses: <b>class A, B, C, D and E.</b> Each class has a range of valid IP addresses. The value of the first octet determines the class. IP addresses from the first three classes (A, B and C) can be used for host addresses. The other two classes are used for other purposes: class D for <b>multicast</b> and class E for <b>experimental purposes.</b><br>
The system of IP address classes was developed for the purpose of Internet IP addresses assignment. The classes created were based on the network size. For example, for the small number of networks with a very large number of hosts, the <b>class A</b> was created. The <b>class C</b> was created for numerous networks with small number of hosts. Classes of IP addresses are:

CLASS     | FIRST OCTET VALUE | SUBNET MASK
:-------- | :---------------- | :-----------
A         | 0 - 126           | 8
B         | 128 - 191         | 16
C         | 192 - 223         | 24
D         | 224 - 239         | -
E         | 240 - 255         | -

For the IP addresses for Class A, the first 8 bits represent the network part, while the remaining 24 bits represent the host part. For class B, the first 16 bits represent the network part, while the remaining 16 bits represent the host part. FOor Class C, the first 24 bits represent the network part, while the remaining 8 bits represent the host part.

### What is TCP?
<b>Transmission Control Protocol (TCP)</b> is a communications standard that enables application programs and computing devices to exchange messages over a network. It is designed to send packets across the Internet and <b>ensure the successful delivery of data and messages</b> over networks.<br>
TCP is one of the basic standards that define the rules of the Internet and is included within the standards defined by the Internet Engineering Task Force (IETF). It is one of the most commonly used protocols withing digital network communications and <b>ensures end-to-end data delivery.</b><br>
<br>
TCP organizes data so that it can be transmitted between <b>a server and a client</b>. It guarantees the integrity of the data being communicated over a network. Before it transmits data, TCP establishes a connection between a source and its destination, which it ensures remains live until communicatoin begins. It then breaks large amounts of data into smaller packets, while ensuring data integrity is in place throughout the process.<br>
<br>
As a result, <b>TCP is used to transmit data from high-level protocols that need all data to arrive</b>. These include peer-to-peer sharing protocols like <b>File Transfer Protocol (FTP), Secure Shell (SSH), and Telnet</b>. It is also used to send and receive email through <b>Internet Message Access Protocol (IMAP), Post Office Protocol (POP), and Simple Mail Transfer Protocol (SMTP)</b> and for web access through the <b>Hypertext Transfer Protocol (HTTP)</b>.<br>

### What is UDP?
The User Datagram Protocol, or UDP, is a communication protocol used across the Internet for especially time-sensitive transmissions such as video playback or DNS lookups. It speeds up communications by not formally establishing a connection before data is transferred. This allows data to be transferred very quickly, but it can also cause packets to become lost in transit.<br>
Like all networking protocols, UDP is a standarized method for transfering data between two computers in a network. Compared to other protocols, UDP accomplishes this process in a simple fashion: it sends packets (units of data transmission) directly to a target computer, without establishing a connection first, indicating the order of said packets, or checking whether they arrived as intended. <b>UDP packets are referred to as "datagrams"</b>.

### What are the network layers? What is the OSI model?
In computer science, the concept of network layers is a framework that helps to understand complex network interactions. There are two models that are widely referenced today: <b>OSI and TCP/IP</b>. The concepts are similar, but layers themselves differ between the two models.<br>
<br>
While TCP/IP is the newer model, the <b>Open Systems Interconnection (OSI)</b> model is still referenced a lot to describe network layers. The <b>OSI model</b> was developed by the <b>International Organization of Standarization</b>. There are 7 layers:
<ol>
    <li><b>Physical</b> --> cable</li>
    <li><b>Data Link</b> --> MAC</li>
    <li><b>Network</b> --> IP, routers</li>
    <li><b>Transport</b> --> TCP, UDP</li>
    <li><b>Session</b> --> Syn/Ack</li>
    <li><b>Presentation</b> --> ASCII, PNG</li>
    <li><b>Application</b> --> SNMP, HTTP, FTP</li>
</ol>
The <b>TCP/IP model</b> is a more concise framework, with only 4 layers</b>:
<ol>
    <li><b>Network Access</b></li>
    <li><b>Internet</b></li>
    <li><b>Transport</b></li>
    <li><b>Application</b></li>
</ol>
<br>
Anything that has to do with inter-network connections takes place at the network layer. This includes up the routes for data packets to take, checking to see if a server in another network is up and running, and addressing and receiving IP packets from other networks. This last process is perhaps the most important, as the vast majority of Internet traffic is sent over IP.<br>

### What is a DHCP server and the DHCP protocol?
A <b>DHCP Server</b> is a network sever that automatically provides and assigns IP addresses, default gateway and other network parameters to client devices. It relies on the standard protocol known as <b>Dynamic Host Configuration Protocol</b> to respond to broadcast queries by clients.<br>
A DHCP server automatically sends the required network parameters for clients to propertly communicate on the network. Without it, the network administrator has to manually set up every client that joins the network, which can be cumbersome, especially in large networks. DHCP servers usually assign each client with a unique dynamic IP address, which changes when the client's lease for that IP address has expired.<br>

### What is a DNS server and the DNS protocol?
The <b>Domain Name System (DNS)</b> is the phonebook of the Internet. When users type domain names such as "google.com" into web browsers, <b>DNS is responsible for finding the correct IP address for those sites.</b> Browsers then use those addresses to communicate with origin servers or CDN edge servers to access website information. This all happens thanks to DNS servers: machines dedicated to answering DNS queries.<br>

### What are the rules to make 2 devices communicate using IP addresses?

### How does routing work with IP?

### What is a default gateway for routing?

### What is a port from an IP point of view and what is it used for when connecting to another device?


### Bibliography
Kapersky: <a href="https://www.kaspersky.com/resource-center/definitions/what-is-an-ip-address">What is an IP Address - Definition and Explanation</a><br>
Guru: <a href="https://www.guru99.com/difference-ipv4-vs-ipv6.html">IPv4 vs IPv6: What's the Difference?</a><br>
Teltonika: <a href="https://wiki.teltonika-networks.com/view/What_is_a_Netmask%3F">What is a Netmask?</a><br>
Ionos: <a href="https://www.ionos.com/digitalguide/server/know-how/broadcast-address/">What is a broadcast address and how does it work?</a><br>
Keenetic: <a href="https://help.keenetic.com/hc/en-us/articles/213965789-What-is-the-difference-between-a-public-and-private-IP-address-">What is the difference between a public and a private IP address?</a><br>
Digital Ocean: <a href="https://www.digitalocean.com/community/tutorials/understanding-ip-addresses-subnets-and-cidr-notation-for-networking">Understanding IP Addresses, Subnets, and CIDR Notatio for Networking</a><br>
Study-ccna: <a href="https://study-ccna.com/classes-of-ip-addresses/">Classes of IP addresses</a><br>
Fortinet: <a href="https://www.fortinet.com/resources/cyberglossary/tcp-ip">What is a Transmission Control Protocol TCP/IP Model?</a><br>
Cloudflare: <a href="https://www.cloudflare.com/es-es/learning/ddos/glossary/user-datagram-protocol-udp/">What is User Datagram Protocol (UDP/IP)?</a><br>
Plixer: <a href="https://www.plixer.com/blog/network-layers-explained/">The Network Layers Explained</a>
Infoblox: <a href="https://www.infoblox.com/glossary/dhcp-server/">What is a DHCP Server?</a><br>


