# RDP

## nmap

```shell
nmap -oN nmap/scan_3389.logs -p 3389 -sV --script rdp-enum-encryption $ip
```

## clients

```shell
xfreerdp /v:$ip /u:username /p:password
```
