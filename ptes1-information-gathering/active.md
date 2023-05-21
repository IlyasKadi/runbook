# active

## Network discovery

- Arp scan a network.

```
arp-scan -I eth1 10.10.10.10/24
```

- Ping scan / ping sweep a network.

```shell
nmap -sn 10.10.0.0/16
```

- Find DNS server on a network.

```shell
nmap -p 53 --open 10.0.0.0/24
```

- Perform a reverse DNS lookup

```
dig @$dnsIp -x $ip
```

## Target discovery

Different `nmap` scans are listed below.

- Simple port scan.

```shell
nmap -T4 -Pn -oN nmap/basic.logs $ip
```

- All ports scan.

```shell
nmap -T4 -Pn -oN nmap/all.logs -p- $ip
```

- Versioned port scan.

```shell
nmap -Pn -oN nmap/version.logs -sV -p ports $ip
```

- UDP port scan (requires root privileges).

```shell
sudo nmap -T4 -Pn -oN nmap/udp.logs -U $ip
```

- TCP SYN scan (requires root privileges).

```shell
nmap -sS $ip
```
