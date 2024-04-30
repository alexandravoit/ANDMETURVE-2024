# PRAKTIKUM 10

1) Skript
   
        #!/bin/sh
        
        iptables -F
        
        iptables -A INPUT -i lo -j ACCEPT
           
        iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
        
        iptables -A INPUT -s 192.168.8.118 -p icmp --icmp-type echo-request -j ACCEPT
        
        iptables -A INPUT -s 192.168.8.118 -d 192.168.8.117 -p tcp --dport 22 -j ACCEPT
        
        iptables -A INPUT -j DROP

