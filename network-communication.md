
## Networking
<details>
<summary>What are the seven layers of the ISO / OSI?</summary>

The International Organization for Standardization (ISO) developed the Open Systems Interconnection (OSI) model, which allows different communication systems to communicate via standard protocols.

The OSI model is divided into seven layers, as follows

1. **Physical Layer** takes care of transmission and reception of raw bytestreams over a physical medium.
1. **Data Link Layer** performs the most reliable node to node delivery of data. It forms frames from the packets that are received from network layer and gives it to physical layer. It also synchronizes the information which is to be transmitted over the data. Error controlling is easily done. The encoded data are then passed to physical
1. **Network Layer**: controls the source to destination delivery of data packets across multiple nodes (routing). Network layer is implemented by network devices such as routers.
1. **Transport Layer** is responsible for delivery of an entire message from an application program on the source device to a similar application program on the destination device. Protocols are TCP and UDP.
1. **Session Layer** is responsible for establishing, managing, synchronizing and terminating sessions between end-user application processes.
1. **Presentation Layer** ensures that the message is presented to the upper layer in a standardized format. It deals with the syntax and the semantics of the messages (encryption - compression).
1. **Application Layer** is the topmost layer of the OSI model. It specifies the interfaces and supports services to the end users for network access. Some examples are HTTP, FTP and SMTP.

The basic difference between network layer and transport layer is that transport layer protocol provides logical communication between processes running on different hosts , whereas network layer protocol provides logical communication between processes within the same host.
</details>

<details>
<summary>Hub vs switch vs router?</summary>

A **switch**, also known as an Ethernet switch and network switch, is a piece of networking hardware used on WANs and LANs. A switch connects multiple devices on a network and manages packets according to the IP address of the device.

In a network, a **router** is layer-3 networking hardware used at the network layer of the OSI design. A router can connect a network to another network and transfer data between them. Unlike the hub, a router will use IP address information to transfer IP packets.

A **hub** is a simple networking device that connects several devices in a Local Area Network. Unlike the other two devices I have mentioned before, a hub does not filter information. Instead, it copies the incoming data to all the devices connected to the network and vice versa. Network hubs, also known as Ethernet hubs, are also used to enhance the network distance. However, these devices do not recognize the devices based on the IP address. On the other hand, the system simply copies information as a part of the routine.

</details>

<details>
<summary>What are some differences between TCP and UDP?</summary>

* **Transmission control protocol (TCP)** is a connection-oriented protocol, i.e. a connection is established before sending the data and is closed afterwards. 
    * TCP guarantees that the packages are received correctly and in the proper order. 
    * TCP does not support broadcasting.
    * TCP is used by HTTP, HTTPs, FTP, SMTP and Telnet.
    
* **User data protocol (UDP)** is a data-oriented protocol. The data is sent without establishing a connection.
    * UDP just sends data without guarantee that the package order is preserved or is received. Lost packages are not retransmitted.
    * UPD supports broadcasting.
    * UDP is used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP.

To conclude TCP is more reliable than UDP because it offers more control on the data transmission but the price to pay is that TCP is slower.
</details>

<details>
<summary>Why does DNS use UDP and not TCP?</summary>

DNS is an application layer protocol. All application layer protocols use one of the two transport layer protocols, UDP and TCP. TCP is reliable and UDP is not reliable. DNS is supposed to be reliable, but it uses UDP, why? 

  
There are the following interesting facts about TCP and UDP on the transport layer that justify the above. 
1. UDP is much faster. TCP is slow as it requires a 3-way handshake. The load on DNS servers is also an important factor. DNS servers (since they use UDP) don’t have to keep connections. 
1. DNS requests are generally very small and fit well within UDP segments. 
1. UDP is not reliable, but reliability can be added to the application layer. An application can use UDP and can be reliable by using a timeout and resend at the application layer. 
</details>

