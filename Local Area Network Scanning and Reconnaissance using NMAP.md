# NMAP

## Subnet
A subnet or subnetwork is a smaller network within a larger one, each with its own unique IP address range. Subnets make networks more efficient by simplifying routes. Subnetting improves network performance, security and manageability.
The size of a subnet depends on the connectivity requirements and the network technology employed.
## NMAP command to scan the services for the whole subnet.
Command - `nmap -sV <network address>/<subnet prefix/CIDR notation>`

`-sV` - Probe open ports to determine service/version info.

Example - `nmap -sV 192.168.59.133/24`

![image](https://user-images.githubusercontent.com/33444140/226260646-cc8aa426-8de7-481e-83ad-c998fd0aa03a.png)

## Firewall
 A firewall is software or firmware that prevents unauthorized access to a network. Its purpose is to establish a barrier between your internal network and incoming traffic from external sources in order to block malicious traffic like viruses and hackers. Firewalls can be implemented as software, hardware, or a combination of both. They work by examining the packets of network traffic and comparing them against the set of rules or policies defined by the administrator.
 
 ### Types of Firewall
 - Packet-filtering Firewalls
 - Circuit-level Gateways
 - Application-level Gateways (Proxy Firewalls)
 - Stateful Multi-layer Inspection (SMLI) Firewalls
 - Next-generation Firewalls (NGFW)
 - Threat-focused NGFW
 - Network Address Translation (NAT) Firewalls
 - Cloud Firewalls
 - Unified Threat Management (UTM) Firewalls
 ## NMAP command to detect that a firewall protects the host.
  Nmap distinguishes between ports that are reachable but closed, and those that are actively filtered. An effective technique is to start with a normal SYN port scan.
 
 Command - `nmap -sS -p- ipaddress`
 
 `sS` - SYN scan
 
 `-p-` - All ports
 
 Example - `nmap -sS -p- 192.168.59.133`
 ### Unfiltered packets
 ![image](https://user-images.githubusercontent.com/33444140/226264492-c4394a18-4c84-47d9-926f-4a6cbbd0e443.png)
 ### Filtered packets
 ![image](https://user-images.githubusercontent.com/33444140/226266735-ced66c1e-4e1c-42dd-bdb8-347bcf02efa7.png)

## NMAP command to scan a network and determine which devices are up and running.

Command - `nmap -sn <ip>/<CIDR>`

`-sn` - Scanning devices connected to the network.

Example - `nmap -sn 192.168.59.133/24`

![image](https://user-images.githubusercontent.com/33444140/226269403-cd4c9491-fb62-4293-8a18-0609e36f827d.png)
