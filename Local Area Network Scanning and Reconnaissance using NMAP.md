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

## Vertical & Horizontal scan
#### Vertical Scanning 
also known as service scanning, involves scanning a single host for all the open ports and services that are running on it. This approach allows for a detailed analysis of the individual host, including the versions of services running, operating system, and other relevant information.

#### Horizontal Scanning
also known as port scanning, involves scanning multiple hosts for a specific open port or set of ports. This approach allows for a quick overview of the network or hosts that may have a specific service or vulnerability present.

## NMAP command to scan multiple hosts
Adding ip address as hosts into `/etc/hosts` file.

![image](https://user-images.githubusercontent.com/33444140/226356191-a9e4f072-22e2-4a1d-af1c-0acd31915aa2.png)

![image](https://user-images.githubusercontent.com/33444140/226356596-069e7d28-bb7f-4b06-be86-e60cb97d2914.png)

## NMAP command to export the output in XML format
Command - `nmap -sV <ipaddr> -oX filename.xml`

`-oX` - Outputs scan in XML format.

![image](https://user-images.githubusercontent.com/33444140/226360344-3d19f3a8-6723-4f43-8cdf-b207fd6271ec.png)

## NMAP command to get OS information about a host
Command - `nmap -O <target-ip>`

`-O` - to get OS information.

