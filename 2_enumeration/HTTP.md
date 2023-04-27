# HTTP

## nmap

```shell
nmap -oN nmap/80.logs -p 80 -sV --script vuln,http-enum $ip
```
