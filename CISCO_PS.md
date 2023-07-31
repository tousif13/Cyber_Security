# Security Assessment

Below is the network topology that consists of 3 blocks and systems in it interconnected.

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/df612fea-9953-46c4-8c9a-744deb7a4451)

We will go through block by block and analyze the components involved, security risks and their mitigations.

## Block A

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/72aeb650-5617-44bd-becb-15894008208d)

Block A consists of three departments (Admissions, HR and Accounts) which the network is segmented into 3 parts where one system of respective department should be inaccessible to the system in other departments.

### Security Risk : Unauthorized Access

There is a security risk here where a system from one department can access the system in other departments. This leads to the exposure of information where if a person from HR department is accessing Accounts.

#### Proposed Solution

Apart from the respective department systems, other department systems should not be accessible.

We can achieve this by using VLANs and access control lists.

> VLAN stands for "Virtual Local Area Network." It is a technology used in computer networks to logically divide a single physical local area network (LAN) into multiple virtual LANs. These virtual LANs operate as separate entities.

> Access Control Lists (ACLs) are a fundamental security feature used in computer networks to control and manage the flow of traffic between devices. ACLs are employed primarily in routers and firewalls to permit or deny specific types of traffic based on defined rules and conditions. These rules act as filters, determining what traffic can pass through the network and what traffic should be blocked.

#### Steps :

* Create VLANs

      Switch-A(config)# vlan 10
      Switch-A(config-vlan)# name Admissions

      Switch-B(config)# vlan 20 
      Switch-B(config-vlan)# name HR

      Switch-C(config)# vlan 30
      Switch-C(config-vlan)# name Accounts

* Assign ports to VLANs

      Switch-A(config)# interface fastethernet 0/0
      Switch-A(config-if)# switchport mode access
      Switch-A(config-if)# switchport access vlan 10

      Switch-B(config)# interface fastethernet 0/1
      Switch-B(config-if)# switchport mode access
      Switch-B(config-if)# switchport access vlan 20

      Switch-C(config)# interface fastethernet 1/0
      Switch-C(config-if)# switchport mode access
      Switch-C(config-if)# switchport access vlan 30


* Configure the router

      Router(config)# interface fastethernet 0/0.10
      Router(config-subif)# encapsulation dot1q 10
      Router(config-subif)# 10.0.0.1 255.0.0.0

      Router(config)# interface fastethernet 0/0.20
      Router(config-subif)# encapsulation dot1q 20
      Router(config-subif)# 11.0.0.1 255.0.0.0

      Router(config)# interface fastethernet 0/0.30
      Router(config-subif)# encapsulation dot1q 30
      Router(config-subif)# 12.0.0.1 255.0.0.0

* Create Access Control Lists with the respective IP addressess

      Router(config)# access-list 100 deny 11.0.0.1 0.0.0.0 12.0.0.1 0.0.0.0
      Router(config)# access-list 100 permit ip any any

* Apply ACL to VLAN interfaces

      Router(config)# interface fastethernet 0/0.10
      Router(config-if)# ip access-group 102 in

      Router(config)# interface fastethernet 0/0.20
      Router(config-if)# ip access-group 101 in

      Router(config)# interface fastethernet 0/0.30 
      Router(config-if)# ip access-group 100 in

* Save the configuration and we mitigated the security risk of unauthorized accessing of systems of one department to the system of other department.
