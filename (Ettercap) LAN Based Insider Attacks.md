# Ettercap
## ARP Cache Poisoning
- ARP Cache Poisoning is an attack against an Ethernet or Wi-Fi network to get between the router and the target user.
- In an ARP Cache Poisoning, messages meant for the target are sent to the attacker instead, allowing the attacker to spy on, man-in-the-middle or deny service to a target
- In an ARP poisoning attack, a program like Ettercap will send spoofed messages attempting to get nearby devices to associate the hacker's MAC address with the IP address of the target.
- Sensitive information like passwords can be retrieved using ARP Cache poisoning attack.
## Password stealing using ARP Cache Poisoning attacks
- Open Ettercap tool

- Scan the hosts
<img src="https://user-images.githubusercontent.com/33444140/227280184-f1f40ec1-0382-45ee-b2d6-6b58ef7db4ad.png" height=370>

- Add the victim IP address as Target
<img src="https://user-images.githubusercontent.com/33444140/227280810-1d61df20-81e1-4b99-965e-247089dd9fbb.png" height=370>

- Select ARP Poisoning
- Ettercap will poison the arp cache of the
 two hosts, identifying itself as the other host respectively.
- Once the arp caches are poisoned, the two hosts start the connection, but
 their packets will be sent to ettercap (attacker) window, and it will record them and forward them to the victim's connection.

- Intercepting a password
 Typing credentials in a victim's webpage.

![webpage](https://user-images.githubusercontent.com/33444140/227282575-5bed5de9-e279-47c1-8964-03674055cdb4.png)

We can see the password appeared on attacker's screen as Ettercap successfully poisoned the target and intercepted the HTTP login request for password.

![passwd](https://user-images.githubusercontent.com/33444140/227282877-4becbe59-7072-4281-9209-2e1a46dcd772.png)

## Denial of Service (DOS) attacks using ARP Cache Poisoning attacks

Denial of service (DOS) is a cyber attack designed to render a service inaccessible.

DOS attacks accomplish this by flooding the target with traffic, or sending it information that triggers a crash.

Flood attacks occur when the system receives too much traffic for the server to buffer, causing them to slow down and eventually stop.

- Open ettercap tool and scan the hosts.
- Select the victim's IP and Gateway address as Targets.
- Start the MITM attack of ARP poisoning.
- Select the `dos_attack` plugin from the plugins list.
- Give victim's IP and fake host IP addresses.

![dos2](https://user-images.githubusercontent.com/33444140/227770389-2ebc7569-e380-4888-b891-4ca882166a77.png)

- Check accessing any site in the victim's web. DOS makes the service inaccesible.

![dos](https://user-images.githubusercontent.com/33444140/227770561-20c7b3c4-8087-408e-bbb6-21671165ca99.png)

- If there's no any DOS is implemented. then, we can access the site normally.

![dos3](https://user-images.githubusercontent.com/33444140/227770698-33bf4815-8cb4-4f27-a1dc-1d3793683723.png)
 
## DNS Spoofing attack using ARP Cache Poisoning attacks
 DNS spoofing is the act of entering false information into a DNS cache, so that DNS queries return an incorrect response and users are directed to the wrong websites.
 The attacker can poison ARP tables and force targeted user devices into using the attacker-controlled machine as the server for a specific website.
 
 First we need to configure some information to perform the DNS spoofing.
 - Open the `/etc/ettercap/etter.conf` file.
 - We have to change the uid, gid values to 0 and remove the # from of IPtables section to active the commands.
 
 ![dnsspoof4](https://user-images.githubusercontent.com/33444140/227757608-b039d48f-2cff-4f52-802c-954845322775.png)

![dnsspoof3](https://user-images.githubusercontent.com/33444140/227757632-62afa7cb-be5b-432c-b005-418716c47b9f.png)
- Then, we open `/etc/ettercap/etter.dns` file and entry the website domain and our (attacker's) IP associated to it.

![dnsspoof5](https://user-images.githubusercontent.com/33444140/227757716-01f01e6f-c9df-430b-b30b-a288ddfb2d66.png)

- Save it and start our apache web server `systemctl start apache2`.
- Open ettercap and scan the hosts.
- Select the victim's IP and Gateway address as Targets.
- Select the `dns_spoof` plugin from the plugins list.
- Start the MITM attack of ARP poisoning.

![dnsspoof2](https://user-images.githubusercontent.com/33444140/227757848-fb2ec0fb-45ea-47ef-83b1-6088a0c543b0.png)

![dnsspoof1](https://user-images.githubusercontent.com/33444140/227757854-a00b82e1-3492-41d7-92f2-82532c727f88.png)

We can see the localhost page of attacker's machine is spoofed to given dns (`tousif.com`) in the victim's webpage.

## Invoke sslstrip tool for stripping the HTTPS connection.

SSL (Secure Sockets Layer) is a standard security technology for establishing an encrypted link between a server and a client like a web browser.

SSL stripping attack is a type of cyber attack in which attackers downgrade a web connection to the less secure HTTP, from the more secure HTTPS.

SSL stripping can lead to security risks like eavesdropping, altering data, communications without any knowledge from legitimate users, etc.

- Open ettercap tool and scan the hosts.
- Select the victim's IP address as Target.
- Start the MITM attack of ARP poisoning.
- Select the `sslstrip` plugin from the plugins list.

![ssls](https://user-images.githubusercontent.com/33444140/227933924-1b3148b3-a46d-440c-a2d7-476e035a5917.png)

- We can see the website's SSL is stripped in the victim's machine.

![ssl](https://user-images.githubusercontent.com/33444140/227934370-5d456553-8d28-4f17-9d69-396ce037aa2a.png)

## arp_cop and scan_poisoner plugins to learn about the detection of ARP attacks
### arp_cop

It reports suspicious ARP activity by passively monitoring ARP requests and replies.

It can report ARP posioning attempts, or simple IP-conflicts or IP-changes.

- Open ettercap and select the `arp_cop` plugin.
- Open ettercap in another machine and scan the hosts.
- Add the first machine's IP address as Target.

![5a](https://user-images.githubusercontent.com/33444140/227994382-01e0c5cd-b79e-49ac-8aa0-851c322c6ddc.png)

- Start the ARP poisoning in second machine.
- We can see in first machine's window that it reports the ARP activity.

![5b](https://user-images.githubusercontent.com/33444140/227994725-642d6747-3bff-42bf-9083-0e58f904e0e8.png)
![5c](https://user-images.githubusercontent.com/33444140/227994777-7508dfbe-36be-40f9-9fcf-3b3e6be1cca3.png)

### scan_poisoner

Scan Poisoner scans if someone is poisoning between the user machine and the hosts in the scanned list.

It checks whether if two hosts in the list have same MAC address.

> We have to build hosts list to perform this check. After that, it sends icmp echo packets to each host in the list and checks if the source mac address of the reply differs from the address we have stored in the list for that ip. To check if someone is poisoning that host pretending to have our ip address and forwards intercepted packets to us.

- Open ettercap and select the `scan_poisoner` plugin.
- Open ettercap in another machine and scan the hosts.
- Add the first machine's IP address as Target.
- Start the ARP Poisoning.
- We can see that one host is replying to other in the lists of hosts that captured by scan_poisoner.

![5d](https://user-images.githubusercontent.com/33444140/227997985-ee25f06e-ca46-4931-ab3c-e0da3259b045.png)
