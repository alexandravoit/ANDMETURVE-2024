# PRAKTIKUM 10

1) Skript
   
        #!/bin/sh
        
        iptables -F
        
        iptables -A INPUT -i lo -j ACCEPT
           
        iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
        
        iptables -A INPUT -s 192.168.8.118 -p icmp --icmp-type echo-request -j ACCEPT
        
        iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
        
        iptables -A INPUT -j DROP

2) Skript
   
            #!/bin/sh
            
            iptables -F
            iptables -X naabrid
            
            iptables -N naabrid
            
            
            iptables -A INPUT -i lo -j ACCEPT
            
            
            iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
            
            
            iptables -A INPUT -s 192.168.8.118 -p icmp --icmp-type echo-request -j ACCEPT
            
            
            iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
            
            
            iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p icmp -j ACCEPT
            iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
            iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 80 -j ACCEPT
            iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 443 -j ACCEPT
            iptables -A naabrid -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 25 -j ACCEPT
            iptables -A naabrid -j RETURN
            
            
            iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -j naabrid
            
            
            iptables -A naabrid -j LOG --log-prefix “Voit-NAABRID-ahel"
            
            
            iptables -A INPUT -j DROP
