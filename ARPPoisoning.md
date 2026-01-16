# ARP Poisoning Lab

## **Aim:**
To learn about MitM (Man in the Middle) attack, catch traffic from a host inside the same local network, and analyse catched data. Learn about different protocols and their security levels.

## **Method:**
	1. Set up a safe environment: Use Kali Linux VM, connect mobile host to the network.
	2. Set & Use Tools: Use Nmap for host discovery, Arpspoof & Wireshark to sniff traffic.
	3. Analysis & Documentation: Use A-Packets to analyse data and document results.

## **Results:**
Nmap has successfully found the target (my phone) and its IP address (192.168.1.125). It has also discovered my router's IP address (192.168.1.254).

![Pinging hosts within the network using Nmap] (searchingHots.png)

I have then used arpspoof to re-direct traffic to/from the target device, to the Kali interface.

![Forwarding all data sent to targets IP] (phoneIPforwarding.png)

Wireshark successfully catched packets with TCP/UDP protocols, and i exported them for further analysis in A-Packets.

![Sniffing results in Wireshark] (wiresharkResults.png)

Packets sent through the HTTP over TCP protocol were not encrypted, therefore easily understood.

## **Conclusion:**
As the result of this investigation, protocols not using SSL or TLS connections, are not secure, as has been proved in case of data capturing, it can be easily read and used for malicious purposes. ARP poisoning method allows attackers to re-direct traffic by confusing the router and target, placing themselves in the middle of the formed traffic chain. Main prevention from these attacks are encrypted communication protocols such as TLS/HTTPS.

## **Next steps:**
Learn how to use ettercap to automatise traffic sniffing process, instead of doing it manually. This tool can also auto-detect vulnerable packets that use HTTP/TELNET. It also allows learning about traffic altering.
