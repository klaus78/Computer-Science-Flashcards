## Protocols

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

