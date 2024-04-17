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

![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/d9c48b71-2728-4168-8691-c76597e0f1e3)

![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/42e094d0-acff-4296-8ca1-13b8c2a1bff9)

Ül 3
1.
Neighbor Discovery Protocol (NDP) haavatavused: NDP-d kasutatakse IPv6 võrkudes naaberseadmete avastamiseks ja marsruutimistabelite haldamiseks. Ründajad saavad kasutada NDP turvaauke, et käivitada erinevaid rünnakuid, nagu Neighbor Discovery Spoofing (Est.k Naabrite avastamise võltsimine), Router Advertisement Spoofing (Est.k Ruuteri Reklaamide Võltsimine) ja Neighbor Cache Poisoning (Est.k Naabri Vahemälu Mürgitamine).

Killustumine ja uuesti kokkupanemine: IPv6 võimaldab IPv4-ga võrreldes suuremaid pakette, mis võib edastuse ajal põhjustada pakettide killustumist. Killustamisega seotud rünnakud, nagu Fragmentation Off Path Attack (Est.k killustumise teelt väljas rünnak) ja Packet Reassembly Attack (Est.k pakettide uuesti kokkupanemise rünnak), võivad ära kasutada IPv6 pakettide killustamise ja uuesti kokkupanemise mehhanismide nõrkusi.

Üleminekumehhanismid: IPv4-lt IPv6-le üleminekul kasutatakse kahe protokolli ühilduvuse tagamiseks erinevaid üleminekumehhanisme, nagu topeltpinu, tunneldamine ja tõlkimine. Need mehhanismid tekitavad täiendavat keerukust ja potentsiaalseid turvaauke. Näiteks saab tunneliprotokolle, nagu 6to4 ja Teredo, kasutada varjatud suhtluseks või turvakontrollist möödahiilimiseks.

