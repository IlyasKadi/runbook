# active

## Active information gathering

Different `nmap` scans are listed below.

- Simple port scan.

```shell
nmap $ip
```

- Vulnerable port scan.

```shell
nmap -sV --script=vuln -p ports $ip
```

- All ports scan.

```shell
nmap -p- $ip
```

- UDP port scan.

```shell
nmap -U $ip
```

- TCP SYN scan (requires root privileges).

```shell
nmap -sS $ip
```

- Ping scan / ping sweep a network.

```shell
nmap -sn 10.10.0.0/16
```
