# active

## Active information gathering

Different `nmap` scans are listed below.

- Simple port scan.

```shell
nmap -oN nmap/basic.logs $ip
```

- All ports scan.

```shell
nmap -oN nmap/all.logs -p- $ip
```

- Versioned port scan.

```shell
nmap -oN nmap/version.logs -sV -p ports $ip
```

- UDP port scan (requires root privileges).

```shell
sudo nmap -oN nmap/udp.logs -U $ip
```

- TCP SYN scan (requires root privileges).

```shell
nmap -sS $ip
```

- Ping scan / ping sweep a network.

```shell
nmap -sn 10.10.0.0/16
```

- Find DNS server on a network.

```shell
nmap -p 53 --open 10.0.0.0/24
```
