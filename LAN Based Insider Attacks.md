# Ettercap
## ARP Cache Poisoning
- ARP Cache Poisoning is an attack against an Ethernet or Wi-Fi network to get between the router and the target user.
- In an ARP Cache Poisoning, messages meant for the target are sent to the attacker instead, allowing the attacker to spy on, man-in-the-middle or deny service to a target
- In an ARP poisoning attack, a program like Ettercap will send spoofed messages attempting to get nearby devices to associate the hacker's MAC address with the IP address of the target.
- Sensitive information like passwords can be retrieved using ARP Cache poisoning attack.
## Password stealing using ARP Cache Poisoning attacks
- ### Open Ettercap tool
<img src="https://user-images.githubusercontent.com/33444140/227277918-24e86e97-7d50-4fdb-abea-1ad11adc7135.png" width=550 height=250>

- ### Scan the hosts
<img src="https://user-images.githubusercontent.com/33444140/227280184-f1f40ec1-0382-45ee-b2d6-6b58ef7db4ad.png" height=370>

- ### Add the victim IP address as Target
<img src="https://user-images.githubusercontent.com/33444140/227280810-1d61df20-81e1-4b99-965e-247089dd9fbb.png" height=370>

- ### Select ARP Poisoning
![arppos](https://user-images.githubusercontent.com/33444140/227282308-cffefeec-bb7a-432b-a1dd-a5dc7f04eaad.png)

- ### Intercepting a password
![webpage](https://user-images.githubusercontent.com/33444140/227282575-5bed5de9-e279-47c1-8964-03674055cdb4.png)

We can see the password appeared on attacker's screen as Ettercap successfully poisoned the target and intercepted the HTTP login request for password.

![passwd](https://user-images.githubusercontent.com/33444140/227282877-4becbe59-7072-4281-9209-2e1a46dcd772.png)

## Denial of Service (DOS) attacks using ARP Cache Poisoning attacks
