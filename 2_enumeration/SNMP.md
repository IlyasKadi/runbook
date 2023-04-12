# SNMP

## nmap

```shell
sudo nmap -oN nmap/161.logs -sU -p 161 -sV --script snmp-win32-services $ip
```

## clients

```shell
snmpwalk -v 2c $ip -c public
```
