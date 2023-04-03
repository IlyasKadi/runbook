# SSH

## nmap

```shell
nmap -oN nmap/22.logs -p 22 -sV --script ssh2-enum-algos $ip
```

Other scripts are

```shell
ssh-hostkey
ssh-auth-methods
```
