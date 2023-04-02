# FTP

## nmap

```shell
nmap -oN nmap/scan_21.logs -p 21 -sV --script ftp-anon $ip
```

## clients

- Check anonymous log in.

```shell
ftp anonymous@$ip
```

- Check for vulnerabilities found during `nmap` enumeration.
- Check common credentials

```shell
hydra \
  -L /usr/share/seclists/Username/top-usernames-shortlist.txt \
  -P /usr/share/seclists/Passwords/darkweb2017-top100.txt \
  $ip ftp
```

- Brute force. 

## Helpers

- If you get the message

```
229 Entering Extended Passive Mode (|||46829|)
```
then make sure to turn off passive mode.

- Recursively download from FTP server using 

```shell
wget -r ftp://username:password@$ip
```
