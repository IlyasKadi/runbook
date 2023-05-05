# 9_common_software

## Wordpress

Bare bone scan.

```shell
wpscan --url http://$ip
```

Enumerate users on the CMS.

```shell
wpscan --url http://$ip --enumerate u
```

Perform password attack.

```shell
wpscan --url http://$ip --usernames users.txt --passwords passwords.txt
```
