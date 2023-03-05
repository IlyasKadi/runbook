# 1 nmap

- Simple port scan.

```shell
nmap -oN nmap/scan.logs $ip
```

- Vulnerable port scan

```shell
nmap -oN nmap/scan_vuln.logs -sV --script=vuln -p ports $ip
```

- All ports scan.

```shell
nmap -oN nmap/scan_all.logs -p- $ip
```
