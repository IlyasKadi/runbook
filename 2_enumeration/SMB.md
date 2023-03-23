# SMB

## nmap

Enumerate SMB with nmap using

````shell
nmap -oN nmap/scan_SMB.logs -p 445 --script smb-protocols $ip
````

Other scripts that can be used are

```shell
smb-security-mode
smb-enum-sessions
```

## clients

- Check available shares

```shell
smbclient -U anonymous -L $ip
```

- Check indivual share

```shell
smbclient -U anonymous //$ip/sharename
```

- Check for null sessions [https://en.wikipedia.org/wiki/Null_session](https://en.wikipedia.org/wiki/Null_session) by running

```shell
smbclient -U anonymous //$ip/IPC$
```
- Automated enumeration using `enum4linux`.

- Enumerate shares blindly using

```shell
enum4linux -s /usr/share/wordlists/rockyou.txt $ip
```

## Helpers

To download a full directory using the `smbclient`, run

```shell
smbclient -U username $ip password
smb: \> prompt off
smb: \> recurse on
smb: \> mget dir
```
