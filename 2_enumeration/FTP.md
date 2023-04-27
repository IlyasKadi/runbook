# FTP

## nmap

```shell
nmap -oN nmap/21.logs -p 21 -sV --script ftp-anon $ip
```

## clients

- Check anonymous log in.

```shell
ftp anonymous@$ip
```

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
