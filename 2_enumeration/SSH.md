# SSH

## nmap

```shell
nmap -oN nmap/scan.logs -p 22 --script=ssh2-enum-algos $ip
```

Other scripts that can be used are

```shell
ssh-hostkey
ssh-auth-methods
```
