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

### What are the differences between public and private IPs?
The are different categories of IP addresses, and within each category different types. This time, we are going to focus on public and private IPs:
<ul>
  <li>Private IP addresses: every device that connects to your Internet network has a private IP address. This includes </li>
  
</ul>

### What is a class of IP addresses?

### What is TCP?

### What is UDP?

### What are the network layers?

### What is the OSI model?

### What is a DHCP server and the DHCP protocol?

### What is a DNS server and the DNS protocol?

### What are the rules to make 2 devices communicate using IP addresses?

### How does routing work with IP?

### What is a default gateway for routing?

### What is a port from an IP point of view and what is it used for when connecting to another device?

### Extra information
IP addresses are not random. They are mathematically produced and allocated by the Internet Assigned Numbers Authority (IANA), a division of the Internet Corporation for Assigned Names and Numbers (ICANN). ICANN is a non-profit organization that was established in the United States in 1998 to help maintain the security of the Internet and allow it to be usable by all.

### Bibliography
Kapersky: <a href="https://www.kaspersky.com/resource-center/definitions/what-is-an-ip-address">What is an IP Address - Definition and Explanation</a><br>
Guru: <a href="https://www.guru99.com/difference-ipv4-vs-ipv6.html">IPv4 vs IPv6: What's the Difference?</a>
Teltonika: <a href="https://wiki.teltonika-networks.com/view/What_is_a_Netmask%3F">What is a Netmask?</a>
Ionos: <a href="https://www.ionos.com/digitalguide/server/know-how/broadcast-address/">What is a broadcast address and how does it work?</a>
