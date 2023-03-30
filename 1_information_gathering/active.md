# active

## Active information gathering

Different `nmap` scans are listed below.

- Simple port scan.

```shell
nmap -oN nmap/scan_basic.logs $ip
```

- All ports scan.

```shell
nmap -oN nmap/scan_all.logs -p- $ip
```

- Versioned port scan.

```shell
nmap -oN nmap/scan_version.logs -sV -p ports $ip
```

- UDP port scan.

```shell
nmap -oN nmap/scan_udp.logs -U $ip
```

- TCP SYN scan (requires root privileges).

```shell
nmap -sS $ip
```

- Ping scan / ping sweep a network.

```shell
nmap -sn 10.10.0.0/16
```
