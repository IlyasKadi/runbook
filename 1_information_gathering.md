# 1 information gathering

## Passive information gathering

- Get domain registrar information
```shell
whois example.com
```

- Disover hosts related to a domain using [https://dnsdumpster.com/](https://dnsdumpster.com/).

- Perform a DNS zone transfer using

```shell
dig -t AXFR example.com @$ip
```

- Enumerate DNS zone (such as cached records) using the `dnsrecon` tool

```shell
dnsrecon --domain example.com
```

## Active information gathering

Different `nmap` scans are listed below.

- Simple port scan.

```shell
nmap $ip
```

- Vulnerable port scan

```shell
nmap -sV --script=vuln -p ports $ip
```

- All ports scan.

```shell
nmap -p- $ip
```

- UDP port scan

```shell
nmap -U $ip
```

- TCP SYN scan (requires root privileges)

```shell
nmap -sS $ip
```
