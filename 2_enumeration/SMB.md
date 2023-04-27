# SMB

## nmap

````shell
nmap -oN nmap/445.logs -p 445 -sV \
  --script=vuln,smb-enum-shares,smb-enum-users,smb-os-discovery,smb-protocols $ip
````

## clients

- Check available shares.

```shell
smbclient -U anonymous -L $ip
```

- Check for individual share.

```shell
smbclient -U anonymous //$ip/sharename
```

- Automated enumeration using `enum4linux`.

- Enumerate shares blindly using

```shell
enum4linux -s /usr/share/wordlists/rockyou.txt $ip
```

- Gain a meterpreter shell using the `exploit/windows/smb/psexec` metasploit module.
- Interact with SMB from a windows host.

```shell
net view $ip
net use D: \\$ip\sharename
```

## Helpers

To download a full directory using the `smbclient`, run

```shell
smbclient -U username $ip password
smb: \> prompt off
smb: \> recurse on
smb: \> mget dir
```
