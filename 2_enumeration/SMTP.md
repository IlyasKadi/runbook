# SMTP

## nmap

```shell
nmap -oN nmap/25.logs -p 25 -sV --script vuln,smtp-commands $ip
```
