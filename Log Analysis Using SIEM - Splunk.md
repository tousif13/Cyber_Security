# Splunk

## Installation

![install](https://github.com/tousif13/Cyber_Security/assets/33444140/45ae140a-51df-4889-a4e9-05ea12cac392)

![install2](https://github.com/tousif13/Cyber_Security/assets/33444140/c8396586-af93-4949-9052-d516b00a237d)

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/9d7defe9-29ad-4e3e-90a5-887a055fd42b)

## Configuring

### Adding forwarder to the splunk enterprise

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/57ba8a50-d28c-4c80-bc53-63645096fb07)

### Enabling splunk forwarder

* Go to manage apps and enable the splunk forwarder

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/bf4f8057-8d7a-4f8c-9a66-d2b21549f74c)

## Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) Make sure the logs are indexing in the Splunk enterprise.

*  Run any network and port scanning commands from the host to the target machine.

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/7c68fea2-ee65-418c-b352-f0a425aa9cb5)

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/f7a344ee-1e36-486d-92d1-c03070ab9cb1)

Now as we performed the scan we can see the nmap logs by using `scan` in search

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/720f1e01-0c26-4b4f-b665-d3eac50a6864)

## Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) Make sure the logs are indexing in the Splunk enterprise

* Perform any communication using unencrypted traffic.

* Visiting an unencrypted site

![dnsspoof1](https://github.com/tousif13/Cyber_Security/assets/33444140/e08b51df-0dd9-4c31-b90e-ee7e53b7ccab)

* Now we add monitor of log files to splunk

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/d810b314-3849-4d01-9e2a-165e388d179b)

* We can see the http logs here.

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/4d496889-66a8-48a0-a93c-3d1b87ac4c4f)

* We can see the get requests here.

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/2b62acf4-4b6f-409f-99b7-cfbfdea34116)

## Run Splunk >> Forwarder can be in the same system or another system (user’s convenience)  >>Make sure the logs are indexing in the Splunk enterprise.

*  Logout of the target system and perform multiple failed attempts. Then use the search  section to filter out the failed attempt logs

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/362e081e-3912-491d-92cc-6f96326070e1)

* Now if we search `authentication failure` in search box. it will show the logs.

![image](https://github.com/tousif13/Cyber_Security/assets/33444140/bc05dd4e-5dae-429a-82aa-2ba94b06cfa1)
