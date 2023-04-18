## Creating an IPsec-based VPN with the help of the Strongswan tool.

### Enabling kernel packet forwarding 

`sudo vi /etc/sysctl.conf`

![packetforwardpurple](https://user-images.githubusercontent.com/33444140/232818391-c806c2ca-2a78-48d0-92c1-c16ea69b36d5.png)

### Installing / Enabling Strongswan tool

`sudo systemctl enable strongswan-starter`

`sudo systemctl status strongswan-starter`

![strongswan](https://user-images.githubusercontent.com/33444140/232819390-3646cf15-f07f-4a45-8aa8-99efd877d7ca.png)

### Configuring security gateways

`sudo vi /etc/ipsec.conf`

> Kali linux IP - 192.168.59.133

> Purple Kali linux IP - 192.168.59.138

![gateways](https://user-images.githubusercontent.com/33444140/232841060-0a0a21fc-77e8-4c91-9be6-40e922a2c497.jpeg)


* config setup – specifies general configuration information for IPSec which applies to all connections.
* charondebug – defines how much Charon debugging output should be logged.
* uniqueids – specifies whether a particular participant ID should be kept unique.
* conn prodgateway-to-devgateway – defines connection name.
* type – defines connection type.
* auto – how to handle connection when IPSec is started or restarted.
* keyexchange – defines the version of the IKE protocol to use.
* authby – defines how peers should authenticate each other.
* left – defines the IP address of the left participant’s public-network interface.
* right – specifies the IP address of the right participant’s public-network interface.
* ike – defines a list of IKE/ISAKMP SA encryption/authentication algorithms to be used. You can add a comma-separated list.
* esp – defines a list of ESP encryption/authentication algorithms to be used for the connection. You can add a comma-separated list.
* aggressive – states whether to use Aggressive or Main Mode.
* keyingtries – states the number of attempts that should be made to negotiate a connection.
* ikelifetime – states how long the keying channel of a connection should last before being renegotiated.
* lifetime – defines how long a particular instance of a connection should last, from successful negotiation to expiry.
* dpddelay – specifies the time interval with which R_U_THERE messages/INFORMATIONAL exchanges are sent to the peer.
* dpdtimeout – specifies the timeout interval, after which all connections to a peer are deleted in case of inactivity.
* dpdaction – defines how to use the Dead Peer Detection(DPD) protocol to manage the connection.

### Configuring PSK for Peer-to-Peer Authentication.

`sudo vi /etc/ipsec.secrets`

![secrets](https://user-images.githubusercontent.com/33444140/232827004-eccd8b82-3c39-43e1-b6de-2ad5284269a6.png)

### Establishing connection between two gateways

`sudo ipsec restart`

`sudo ipsec up <config-name>`

