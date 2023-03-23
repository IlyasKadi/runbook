# SSH

## nmap

```shell
nmap -oN nmap/scan.logs -p 22 --script=ssh2-enum-algos $ip
```

```shell
nmap -oN nmap/scan.logs -p 22 --script=ssh-hostkey $ip
```
