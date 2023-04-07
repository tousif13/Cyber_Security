# Wi-Fi
Wi-Fi stands for Wireless Fidelity. It is used to connect devices to the internet. It is known as IEEE 802.11

Wi-Fi is which it sents a radio signal to a nearby device, which decodes the signal received. The device transmits a radio signal back to the router.

They transmit at frequencies of 2.4 GHz or 5 GHz.The 2.4 band may be faster for a user connecting to a router several rooms away, while 5 GHz will definitely be faster for a close connection.

Types of Wi-Fi

* `802.11b` - Slowest and least expansive standard. It transmits at 2.4GHz frequency. It uses complementary code keying (CCK) modulation to improve speeds.
* `802.11g` - Transmits at 2.4GHz frequency, but it is faster than 802.11b in handling megabits of data per second.
* `802.11a` - Transmits at 5GHz frequency. It uses orthogonal frequency-division multiplexing (OFDM), that splits radio signal into several sub signals to reduce interferences.
* `802.11n` - It is backward compatible with a,b and g. It significantly improved speed and range over its predecessors. Reportedly it can achieve speeds as high as 140 megabits per second and can transmit up to four streams of data.
* `802.11ac` - Transmits at 5GHz frequency. It allows for transmission on multiple spatial streams upto eight. It is far faster than its predecessors as it is called as 5G or Gigabit WiFi.
* `802.11ax` - Also known as WiFi 6. Allows an even higher data flow rate upto 9.2 Gbps. Accepts multiple devices also connect on a higher 6 GHz band.
* `802.11be` - Projected to be the standard by 2024, should offer better range, faster data rates and more connections than its previous versions.

Attacks on Wi-Fi 

* `Denial-of-Service (DOS) Attack` - DOS attack is which flooding the Wi-Fi network with more no of requests that overloads the network and prevents the users from accessing it.
* `Man-in-the-Middle (MitM) Attack` - MitM attack intercepts the communication between two devices and the attacker steals the information acting as an eavesdropper.
* `Evil Twin Attack / Rogue Access Point Attack` - This attack involves setting up a fake access point as a legitimate access point. So that user assumes fake access point as a legitimate one and exposes the information to the attacker.
* `Password Cracking Attack` - This attack involves using various password cracking attacks such as Dictionary attacks or Brute Force attacks to guess the Wi-Fi password to attack further after getting access to it.

### Setting up and Configuring Wi-Fi adapter to monitor mode
 
 <img src="https://user-images.githubusercontent.com/33444140/230572198-2ee1c79b-158e-4954-b213-1fd0b08f67b3.png" height=650>
 
## Performing Fingerprinting using Wigle, InSSIDer, Kismet

### InSSIDer
- inSSIDer is a wireless network scanner that can be used to analyze and troubleshoot Wi-Fi networks. 
- It gives information about wireless networks such as signal strength, encryption, channels, and other network parameters. 

![image](https://user-images.githubusercontent.com/33444140/230281037-4dc5aa6f-2074-470b-910b-1d0af166ade4.png)

### Wigle
- WiGLE is a website and mobile app that allows users to find infromation and maps wireless networks. 
- It provides information about the location, SSID, and signal strength of nearby Wi-Fi networks. 

Information of Wi-Fi networks

<img src="https://user-images.githubusercontent.com/33444140/230574664-1f26a864-86bf-4416-a36c-b45dfca007ec.jpeg" height=500>

Geographical location of a particular Wi-Fi network

<img src="https://user-images.githubusercontent.com/33444140/230574992-d1ec80b8-a2a4-49f1-a90e-531953005188.jpeg" height=500>

### Kismet
- Kismet is an open-source wireless network detector, sniffer, and intrusion detection system. 
- It works with any 802.11 wireless network and can be used for packet sniffing, network traffic analysis, and wireless network monitoring. 
- It can capture and analyze wireless network traffic, including the contents of data packets.

SSID's of nearby access points.

<img src="https://user-images.githubusercontent.com/33444140/230577114-e6acd519-d7f7-4a68-bebb-afcc64ac6c83.png" height=500>

BSSID

<img src="https://user-images.githubusercontent.com/33444140/230577870-4d988d06-804a-49a4-bbe0-f0b83c8aa5bd.png" height=500>

Devices per channel

<img src="https://user-images.githubusercontent.com/33444140/230578639-618d3901-e77d-4fd1-b094-968d20a7c089.png">

