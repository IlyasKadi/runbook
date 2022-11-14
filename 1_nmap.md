# 1 nmap

- Simple port scan.

```shell
nmap -oN nmap/scan.logs $ip
```

- Versioned port scan

```shell
nmap -oN nmap/scan_version.logs -sV -p ports $ip
```

- Vulnerable port scan

```shell
nmap -oN nmap/scan_vuln.logs --script=vuln -p ports $ip
```

- All ports scan.

```shell
nmap -oN nmap/scan_all.logs -p- $ip
```
