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
