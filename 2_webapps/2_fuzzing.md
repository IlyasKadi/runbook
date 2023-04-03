# 2_fuzzing

- Run `gobuster` for finding directories on the web server.

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirb/wordlists/common.txt -o gobuster/common.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -o gobuster/medium.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,html,php -o gobuster/extensions.txt
```

- Run `ffuf` for subdomain enumeration. 
