# 2_fuzzing

## Directory busting
- Run `gobuster` for finding directories on the web server.

```shell
gobuster dir -u http://$ip -o gobuster/common.txt -w /usr/share/dirb/wordlists/common.txt 
```

```shell
gobuster dir -u http://$ip -o gobuster/medium.txt -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt 
```

```shell
gobuster dir -u http://$ip -o gobuster/extensions.txt -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,html,php 
```

## Subdomain enumeration

- Run `ffuf` for subdomain enumeration. 
