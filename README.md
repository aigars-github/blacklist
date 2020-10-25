# blacklist
Scanning, spaming or intrusion attempts detected from IPs listed in blacklist.txt file by multiple regional public servers. The list is updated hourly.

To block these ips with iptables:
```
ipset create bots iphash
iptables -A INPUT -m set --match-set bots src -j DROP
while read ip; do ipset add spambots "$ip"; done < blackist.txt
```

If you find this list usefull please by me a coffee at https://www.buymeacoffee.com/aigars
