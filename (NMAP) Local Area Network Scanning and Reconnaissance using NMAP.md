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

### Too many fingerprints
> "Too many fingerprints match this host to give specific OS details" means that the probes are contradictory or too broad. If there are no ports responding to network traffic, nmap cannot effectively fingerprint the OS.

![image](https://user-images.githubusercontent.com/33444140/226379557-bd14971a-7d6e-4c6b-9a17-b4bc8d330997.png)

### OS Detection
![image](https://user-images.githubusercontent.com/33444140/226380146-38e4f3da-5c06-4535-bcbc-fa1a78f2150b.png)

## Ping Sweep
Ping sweeping is a network reconnaissance technique used to determine which IP addresses are alive and responsive on a network. It is often used by network administrators to identify active hosts on a network and to map the network. It involves sending a series of ICMP echo request messages, to a range of IP addresses, usually in a sequential order, to identify which ones are available and can be reached.

## NMAP command to perform ping sweeping
Command - `nmap -sn <network address>/<CIDR>`

`-sn` - Performs ping scan on the target.

![image](https://user-images.githubusercontent.com/33444140/226383216-773a132f-335e-46e5-84c0-082b5bbdd44c.png)

## Web application firewall

- A web application firewall (WAF) is a firewall that monitors, filters and blocks data packets as they travel to and from a website or web application.
- It specifically designed to protect web applications from various types of attacks, such as cross-site scripting (XSS), SQL injection, and other vulnerabilities.
- A WAF can be either network-based, host-based or cloud-based and is often deployed through a reverse proxy and placed in front of one or more websites or applications.

## Performing WAF fingerprint detection using NMAP
Command - `nmap --script http-waf-detect <ipaddr>`

![image](https://user-images.githubusercontent.com/33444140/226404457-b597d45f-f068-49e0-8d1a-972823a594ec.png)

## EXIF Data
- EXIF stands for Exchangeable Image File Format.
- It is a metadata format that is embedded in image files captured by digital cameras and other devices that capture digital images.
- Exif data can also include information about the camera's make, model, the lens used, and the exposure settings, such as shutter speed, aperture, and ISO.

## Finding EXIF data of images on a website using NMAP NSE

![image](https://user-images.githubusercontent.com/33444140/226409136-e734615a-4d49-485c-9671-3354ac70e65a.png)

## Finding all subdomains of the website using NMAP NSE

Command - `nmap --script dns-brute.nse <webaddress>`

`dns-brute` - Enumerates subdomains and their corresponding server IP addresses.

![image](https://user-images.githubusercontent.com/33444140/226412993-575f2371-09a7-4543-be53-737c91931240.png)

## Performing a vulnerability scan on the target host using NMAP NSE

Command - `nmap -sV --script=vuln <target ip>`

![image](https://user-images.githubusercontent.com/33444140/226417616-af471d53-73e3-431b-8a24-5a74001ca215.png)
