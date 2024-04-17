# Tulemüür - iptables, nmap, IPv6  
Server ip 192.168.0.182/24

Kloon ip 192.168.0.191/24  

Ül 1
```
#!/bin/sh
iptables -F 
iptables -X naabrid
iptables -N naabrid

iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

iptables -A INPUT -s 192.168.0.191 -j naabrid 

iptables -A naabrid -j LOG --log-prefix "Pauklin-NAABRID-ahel "

iptables -A naabrid -p icmp --icmp-type echo-request -j ACCEPT

iptables -A naabrid -m state --state NEW -p tcp --dport 22 -j ACCEPT
iptables -A naabrid -m state --state NEW -p tcp --dport 80 -j ACCEPT
iptables -A naabrid -m state --state NEW -p tcp --dport 443 -j ACCEPT
iptables -A naabrid -m state --state NEW -p tcp --dport 25 -j ACCEPT

iptables -A naabrid -j RETURN

iptables -A INPUT -j LOG --log-prefix "input-reject "
iptables -A INPUT -j REJECT

sudo iptables -L -nv --line-numbers
```

Ül 2  
![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/ac5ce6b5-c395-4445-b423-bf3004d62f04)
![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/80d7841f-8d85-4457-b703-07e3409add64)
