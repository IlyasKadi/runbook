# 2_fuzzing

## Directory busting
- Run `gobuster` for finding directories on the web server.

```shell
gobuster dir -u http://$ip -o gobuster/common.txt --no-color -w /usr/share/dirb/wordlists/common.txt 
```

```shell
gobuster dir -u http://$ip -o gobuster/medium.txt --no-color -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt 
```

```shell
gobuster dir -u http://$ip -o gobuster/extens.txt --no-color -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,html,php 
```

## Subdomain enumeration

- Run `ffuf` for subdomain enumeration. 
