# PRAKTIKUM 10

1) Skript
   
         #!/bin/sh
         
         iptables -F
         iptables -X naabrid
         
         iptables -N naabrid
         
         
         iptables -A INPUT -i lo -j ACCEPT
         
         
         iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
         
         iptables -A INPUT -j LOG --log-prefix "input-reject "
         
         
         iptables -A INPUT -s 192.168.8.118 -p icmp --icmp-type echo-request -j ACCEPT
         
         
         iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
         
         
         iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p icmp -j ACCEPT
         iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
         iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 80 -j ACCEPT
         iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 443 -j ACCEPT
         iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 25 -j ACCEPT
         iptables -A naabrid -j RETURN
         
         
         iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -j naabrid
         
         
         iptables -A naabrid -j LOG --log-prefix "Voit-NAABRID-ahel"
         
         
         iptables -A INPUT -j DROP

            
2)  
![image](https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/c143296a-0661-4923-9601-6e7126d9b1f2)

3) 
  - 1. IPv6 võimaldab IPv4-ga võrreldes suuremat paindlikkust pakettide killustamisel ja uuesti kokkupanemisel. Ründajad saavad seda paindlikkust ära kasutada et märkamatult mööda saada turvaseadmetest, näiteks tulemüüridest või IDS-ist. IPv6 toob sisse uued protokollid ja laienduspäised (nt. ICMPv6, ND, MLD), millel on omad turvatagajärjed. Näiteks saab IPv6-s asuvat naabrituvastusprotokolli (NDP) kuritarvitada erinevat tüüpi rünnakute jaoks, sealhulgas aadresside võltsimiseks ja ümbersuunamiseks. Lisaks, kasutades NDP-d, saavad ründajad võrgu topoloogiate kaardistamiseks ja aktiivsete seadmete tuvastamiseks siiski aadressi skannida.
    2. ARP oli asendatud NDP-ga ning arp spoofing oli asendatud "neighbour spoofing"-uga. Source: https://book.hacktricks.xyz/generic-methodologies-and-resources/pentesting-network/pentesting-ipv6
    3. Windows ja UNIX-põhised süsteemid (nagu Linux ja macOS) kasutavad erinevaid lähenemisviise turvamudelitele. Windowsi puhul on traditsiooniliselt kasutatud tugevamaid vaikivaid turvasätteid, sealhulgas aktiveeritud             tulemüür sissetulevate ühenduste blokeerimiseks. UNIX-põhised süsteemid nagu Linux ja macOS eeldavad sageli, et süsteemiadministraator konfigureerib ja kohandab tulemüüri vastavalt oma vajadusele, võimaldades seega            suuremat paindlikkust ja kontrolli turvasätete üle.
    4. Script:
       
            #!/bin/bash
            
            
            ip6tables -F
            ip6tables -X
            
            
            ip6tables -P INPUT DROP
            
            
            ip6tables -A INPUT -i lo -j ACCEPT
            
            ip6tables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
            
            
            ip6tables -A INPUT -p tcp -m multiport --dports 80,443 -j ACCEPT
            
            
            ip6tables -P OUTPUT ACCEPT
            
            
            ip6tables -L -v
            
            exit 0


